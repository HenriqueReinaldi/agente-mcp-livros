---
name: pesquisa-produtos
description: "Use when researching products or books on sales or catalog websites and recording verified results and summaries in a Markdown file."
---

# Pesquisa de Produtos

## Objetivo
Pesquisar produtos em um site de vendas ou catálogo e gerar um resumo organizado em um arquivo Markdown, com os dados verificados e as correspondências dos termos solicitados.

## Entradas
Antes de iniciar, identifique ou confirme:

- **Site:** URL do site a pesquisar.
- **Termos de busca:** nomes ou expressões de cada produto desejado.
- **Filtros:** categoria, faixa de preço, disponibilidade, marca, avaliação ou outros critérios fornecidos pelo usuário.
- **Quantidade de resultados:** máximo de produtos a registrar por termo. Se não for informado, pergunte ou declare um padrão antes da pesquisa.
- **Limite de páginas:** máximo de páginas que podem ser abertas para a busca complementar. Respeite qualquer limite informado pelo usuário; se não houver limite, estabeleça um limite conservador e informe-o.
- **Arquivo de saída:** caminho solicitado pelo usuário; caso não seja indicado, use `resultado-busca.md` no workspace.
- **Resumo:** idioma, tamanho ou critérios solicitados. Se não forem especificados, faça um resumo breve no idioma do usuário para o primeiro resultado de cada termo.

Não presuma filtros, limites ou preferências ausentes quando essa escolha puder alterar materialmente os resultados; peça esclarecimento ou explicite o padrão adotado.

## Etapas
1. Abra o site fornecido usando o navegador disponível e verifique se ele oferece uma caixa de busca.
2. **Se houver busca:** pesquise cada termo separadamente. Aplique os filtros fornecidos e confira os resultados no site.
3. **Se não houver busca:** escolha a categoria mais provável para cada termo, usando as categorias visíveis do próprio site. Registre a categoria escolhida e a justificativa breve.
4. Se a categoria inicial não localizar o produto, abra páginas adicionais pertinentes, uma de cada vez, até encontrar correspondências, atingir a quantidade máxima solicitada ou chegar ao limite de páginas.
5. Conte as páginas conforme o limite definido para a pesquisa. Não contorne o limite usando outra rota, paginação ou categoria sem autorização. Caso o usuário não tenha esclarecido se a página inicial conta no limite, considere-a dentro do limite e informe esse critério.
6. Para cada correspondência, confira os dados na página de resultado ou, quando necessário, na página de detalhes do produto. Registre a categoria atribuída pelo site. Se um campo não estiver disponível, indique `Não informado` em vez de inferi-lo.
7. Para o primeiro resultado de cada termo, consulte a descrição do produto e escreva um resumo com o tamanho e o idioma solicitados. Parafraseie; não apresente texto promocional ou descrição copiada como se fosse resumo próprio. Se não houver descrição, informe essa ausência e não invente conteúdo.
8. Crie ou atualize o arquivo Markdown de saída com os resultados, os termos sem correspondência e o escopo efetivamente pesquisado.

## Regras
- Registre somente produtos realmente encontrados no site e compatíveis com o termo e os filtros. Não invente produtos, atributos, preços, avaliações, disponibilidade, categorias, descrições ou resultados.
- Diferencie uma busca concluída sem correspondências de uma busca incompleta por limite de páginas, bloqueio, erro ou falta de acesso. Indique claramente o que foi e o que não foi consultado.
- Nunca exceda o número máximo de resultados por termo nem o limite de páginas. Pare ao atingir qualquer um deles.
- Não registre dados pessoais de vendedores, como nome civil, telefone, e-mail, endereço ou perfis pessoais. Inclua somente informações de produto necessárias à pesquisa.
- Use a moeda, unidade, escala de avaliação e texto de disponibilidade apresentados pelo site. Não converta valores nem avaliações sem solicitação; se converter, preserve também o valor original e explique a conversão.
- Não trate dados de demonstração como valores representativos do mercado. Se o site alertar que os dados são fictícios ou aleatórios, registre esse aviso.
- Não faça compras, adicione produtos ao carrinho, envie formulários, crie contas ou execute outras ações que alterem o site.
- Respeite as instruções do site, os limites de acesso e as restrições do usuário.

## Formato do arquivo de saída
Use Markdown em UTF-8 e a estrutura abaixo, adaptando os campos à solicitação e ao tipo de produto:

```markdown
# Resultado da pesquisa — <site>

## Escopo e estratégia
- Busca do site: <disponível ou não disponível>
- Estratégia usada: <busca direta ou categoria/paginação>
- Filtros: <filtros aplicados ou nenhum>
- Limite: <máximo de resultados por termo e de páginas>
- Páginas consultadas: <quantidade e categorias/URLs relevantes>
- Observações do site: <avisos relevantes ou nenhum>

## <termo de busca>

| # | Produto | Preço | Disponibilidade | Avaliação | Categoria | Link |
|---|---|---|---|---|---|---|
| 1 | <título verificado> | <valor original> | <texto do site> | <nota e escala> | <categoria> | [Página do produto](<URL>) |

**Resumo do primeiro resultado:** <resumo solicitado, se houver descrição disponível.>

## <outro termo de busca>
...

## Termos sem correspondência
- <termo>: não encontrado nas páginas consultadas; foram verificadas <quantidade> páginas em <categorias ou filtros>.
```

Inclua uma linha por produto, até o máximo definido para cada termo. Se o site não fornecer um campo solicitado, escreva `Não informado`. Se um termo não tiver resultados, mantenha a seção e descreva o escopo percorrido, sem preencher dados de produto fictícios. Remova do modelo os campos que não se aplicarem, mas preserve a rastreabilidade da estratégia, dos limites e das correspondências.
