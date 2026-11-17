# Nexus — MVP local-first

Aplicativo web gratuito de notas em Markdown, links `[[entre notas]]`, backlinks, tarefas, busca, backup e funcionamento offline. Sem login e sem serviços externos.

## Usar

1. Publique os arquivos na raiz de um repositório GitHub.
2. Em **Settings → Pages**, escolha **Deploy from a branch**, branch `main`, pasta `/ (root)`.
3. Abra a URL publicada. O site pode ser instalado como PWA no menu do navegador.

Para rodar localmente, use um servidor HTTP (abrir `index.html` diretamente pode bloquear IndexedDB/Service Worker em alguns navegadores):

```bash
python3 -m http.server 8000
```

Acesse http://localhost:8000.

## Testes manuais

- Criar uma nota, editar, atualizar a página e verificar persistência.
- Criar outra nota e conectar usando `[[Título da nota]]`.
- Ver a conexão e o backlink; navegar entre as notas.
- Criar tarefa, concluir, atualizar a página e conferir o estado.
- Exportar backup, importar e verificar dados.
- Depois de abrir uma vez online, ativar modo offline e atualizar a página.
- Verificar responsividade no celular.

## Segurança e limites

- Dados ficam no IndexedDB do navegador/dispositivo. Limpar dados do site pode apagá-los.
- Backups JSON contêm notas em texto legível: guarde-os com cuidado.
- Não há sincronização entre dispositivos, colaboração, anexos, nem criptografia ponta a ponta.
- O editor usa Markdown básico com prévia e não é ainda um editor visual por blocos.
- A visualização de conexões do MVP é uma lista navegável, não um grafo visual.
- O conteúdo Markdown é escapado antes da renderização para evitar HTML arbitrário.

## Licença

MIT — consulte LICENSE.
