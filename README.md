# Painel Appolus — PWA CSV

Aplicativo PWA configurado para ler automaticamente o CSV informado e se adaptar aos cabeçalhos encontrados.

## Fonte configurada

O `index.html` já contém o link CSV fornecido.

## Recursos incluídos

- Instalação no celular como aplicativo (PWA)
- Layout responsivo para Android, iPhone, tablet e desktop
- Atualização manual e automática quando a conexão volta
- Pesquisa em todos os campos
- Filtro por coluna e valor
- Resumo automático por uma coluna categórica/status detectada
- Listagem em cartões no celular e tabela no desktop
- Paginação
- Cache local do último CSV via IndexedDB para consulta quando a fonte estiver indisponível
- Service Worker para cache da interface

## Como publicar

PWA precisa ser servido por HTTPS (ou localhost para testes). Publique a pasta inteira em uma hospedagem estática, por exemplo:

- GitHub Pages
- Cloudflare Pages
- Firebase Hosting
- Vercel / Netlify

Não basta abrir `index.html` diretamente pelo arquivo do celular, pois Service Worker e instalação PWA exigem uma origem HTTP/HTTPS válida.

## Instalação no Android

Abra a URL publicada no Chrome. O botão "Instalar" será exibido quando o navegador considerar o PWA instalável. Também pode usar o menu do Chrome > Instalar aplicativo / Adicionar à tela inicial.

## Instalação no iPhone

Abra a URL no Safari > Compartilhar > Adicionar à Tela de Início.

## Atenção: CORS

O navegador precisa ter permissão para buscar o CSV em `reports.appolus.com.br`. Se o servidor do CSV bloquear CORS, o PWA exibirá erro na primeira carga. Nesse caso, será necessário adicionar um pequeno proxy no mesmo domínio do PWA ou em Google Apps Script/Cloudflare Worker.
