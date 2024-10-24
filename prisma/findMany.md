```typescript
const result = await prisma.table.findMany()

<ol>
  {result.map((data, index) => (
    <li>
      {data.name}
    </li>
  ))}
</ol>
```
