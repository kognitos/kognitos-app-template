# DataTable Rules

## Golden Rules

- **ALWAYS use the Lattice DataTable** — Never use AG Grid components directly.
- **ALWAYS use exported types** — Never import from `ag-grid-community`.
- **Strongly type all usage** — Define interfaces for data and column definitions.
- **No custom styling** — Use only provided variants and design system tokens.

## Basic Usage

```tsx
import {
  DataTable,
  type IDataTableProps,
  type IDataTableColDef,
  type IDataTableGridOptions,
} from '@kognitos/lattice';

interface IUserData {
  id: number;
  name: string;
  email: string;
  status: 'active' | 'inactive';
}

const columns: IDataTableColDef<IUserData>[] = [
  { field: 'id', headerName: 'ID', width: 80 },
  { field: 'name', headerName: 'Name', flex: 1, filter: true },
  { field: 'status', headerName: 'Status', width: 120, filter: true },
];

function UserTable({ users }: { users: IUserData[] }) {
  return <DataTable<IUserData> data={users} columns={columns} />;
}
```

## Variants

```tsx
// Size
<DataTable size="default" />  // 52px row height (default)
<DataTable size="md" />       // 72px
<DataTable size="lg" />      // 96px

// Visual
<DataTable variant="borderless" />  // No borders (default)
<DataTable variant="bordered" />    // With borders
```

## Typed Event Handlers

```tsx
const gridOptions: IDataTableGridOptions<IUserData> = {
  rowSelection: { mode: 'multiRow' },
  onRowClicked: (event) => {
    // event.data is typed as IUserData
    console.log(event.data.name);
  },
};

<DataTable<IUserData> data={users} columns={columns} gridOptions={gridOptions} />
```

## Custom Cell Renderers

```tsx
const StatusRenderer = ({ data }: IDataTableCellRendererParams<IOrderData>) => (
  <Badge variant={data.status === 'completed' ? 'success' : 'warning'}>
    {data.status}
  </Badge>
);

const columns: IDataTableColDef<IOrderData>[] = [
  { field: 'status', headerName: 'Status', cellRenderer: StatusRenderer },
];
```

## What NOT to Do

```tsx
// ❌ Direct AG Grid imports
import { AgGridReact, ColDef } from 'ag-grid-community';

// ❌ Untyped columns
const columns = [{ field: 'name', headerName: 'Name' }];

// ❌ Custom styling
<DataTable className="my-custom-table" style={{ border: '2px solid red' }} />
```

## Missing Types

If you need a type not exported from Lattice, request it to be added to the design system. Do not import from `ag-grid-community` in application code.
