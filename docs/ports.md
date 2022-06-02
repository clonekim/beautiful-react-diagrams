```js
import Diagram, { useSchema, createSchema } from 'beautiful-react-diagrams';

const initialSchema = createSchema({
  nodes: [
    {
      id: 'node-4',
      content: '화물',
      coordinates: [100, 250],
      outputs: [
        { id: 'port-3', alignment: 'right', name: 'PAS(PAX Ancilar Service)'},
      ],
    },
    {
      id: 'node-1',
      content: '여객',
      coordinates: [100, 50],
      outputs: [
        { id: 'port-1', alignment: 'right', name: 'O&D RMS'},
        { id: 'port-2', alignment: 'right', name: 'SKYPASS'},
      ],
      data: {
        foo: 'bar',
        count: 0,
      }
    },
    {
      id: 'node-2',
      content: 'System',
      coordinates: [300, 150],
      inputs: [
        { id: 'sys-1', alignment: 'left' },
      ],
      outputs: [
        { id: 'sys-2', alignment: 'right' },
      ],
      data: {
        bar: 'foo',
      }
    },
    {
      id: 'node-3',
      content: '여객',
      coordinates: [600, 50],
      inputs: [
        { id: 'port-7', alignment: 'left', name: 'KALIS' },
        { id: 'port-8', alignment: 'left', name: 'KALSALES' },
        { id: 'port-9', alignment: 'left', name: 'BREV(지점수입관리시스템)'},
        { id: 'port-10', alignment: 'left', name: 'NAORA(국제선 환불)'},
        { id: 'port-11', alignment: 'left', name: 'WinLOADs'},
        { id: 'port-12', alignment: 'left', name: '임직원정보(KALMAN)'},
      ],
      data: {
        foo: true,
        bar: false,
        some: {
          deep: {
            object: true,
          }
        },
      }
    },
    {
      id: 'node-5',
      content: '화물',
      coordinates: [600, 350],
      inputs: [
        { id: 'port-21', alignment: 'left', name: 'FSS' },
        { id: 'port-22', alignment: 'left', name: 'ACPS'},
        { id: 'port-23', alignment: 'left', name: 'PFMS'},
        { id: 'port-24', alignment: 'left', name: 'ONEPASS(국내선 공항 체크인 정보 전송)'},
      ],
    },



  ],

  links: [
    { input: 'port-1',  output: 'sys-1' },
    { input: 'port-2',  output: 'sys-1' },
    { input: 'port-3',  output: 'sys-1' },
    { input: 'port-7',  output: 'sys-2' },
    { input: 'port-8',  output: 'sys-2' },
    { input: 'port-9',  output: 'sys-2' },
    { input: 'port-10',  output: 'sys-2' },
    { input: 'port-11',  output: 'sys-2' },
    { input: 'port-12',  output: 'sys-2' },

    { input: 'port-21',  output: 'sys-2' },
    { input: 'port-22',  output: 'sys-2' },
    { input: 'port-23',  output: 'sys-2' },
    { input: 'port-24',  output: 'sys-2' },
  ]
});

const UncontrolledDiagram = () => {
  // create diagrams schema
  const [schema, { onChange }] = useSchema(initialSchema);

  return (
    <div style={{ height: '42.5rem' }}>
      <Diagram schema={schema} onChange={onChange} />
    </div>
  );
};

<UncontrolledDiagram />
```
