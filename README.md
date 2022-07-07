Reconciliação é o nome que se para para o fluxo de renderização do React. Ele ocorre da seguinte forma

1- Gera um nova versão do componente que precisar ser renderizado
2- Campara essa nova versão com a versão anterior já salva
3- Se houver atualização, o react 'renderiza' essa nova versão

- O React atualiza apenas o necessário.

## Memo

Ele faz um comparação shallow compare (Comparação rasa), que verifica se os objetos possuem a mesma referencia. Pra resolver o problema da comparação rasa, basta adicionar uma função no segundo parametro do memo.

Exemplo:

```typescript
export const ProductItem = memo(
  ProductItemComponent,
  (prevProps, nextProps) => {
    return lodash.isEqual(prevProps.product, nextProps.product);
  }
);
```

### Casos de uso do memo:

- Em componentes que renderizam muito
- Quando o componente re-renderiza muitas vezes com as MESMAS props
- Em componentes médios ou grandes
- Pure Functional Componentes
