# Treino — app de academia (PWA)

App de treinos 100% offline. Sem conta, sem servidor de aplicação: são só arquivos estáticos.
Os dados ficam no próprio aparelho (use Perfil → Backup para guardar uma cópia).

Arquivos: `index.html`, `manifest.webmanifest`, `sw.js`, ícones e a pasta `img/` (fotos dos exercícios).

## Publicar no GitHub Pages
```bash
git init && git add . && git commit -m "App de treino"
git branch -M main
git remote add origin https://github.com/SEU_USUARIO/treino.git
git push -u origin main
```
No GitHub: Settings → Pages → Source: "Deploy from a branch" → branch `main`, pasta `/ (root)`.
O endereço será `https://SEU_USUARIO.github.io/treino/` (já com HTTPS).

## Ou no seu servidor Linux
Caddy (HTTPS automático), `Caddyfile`:
```
treino.seudominio.com {
    root * /var/www/treino
    file_server
}
```
Nginx: aponte `root /var/www/treino;` e emita o certificado com `certbot --nginx`.
O iPhone só ativa o modo offline em HTTPS.

## Instalar no iPhone
Safari → abrir o endereço → Compartilhar → **Adicionar à Tela de Início**.
Abra uma vez com internet; depois disso funciona offline.

## Atualizar o app
Altere o `index.html` e mude `V="treino-v2"` em `sw.js` (por exemplo `treino-v3`) para o aparelho baixar a versão nova.

## Créditos das imagens
As fotos de execução em `img/` vêm do projeto aberto **free-exercise-db** (https://github.com/yuhonas/free-exercise-db), de domínio público (Unlicense), redimensionadas para uso no app.
Os botões "Como fazer" e "Buscar vídeo" apenas abrem a busca no Treino Mestre e no YouTube; nenhum conteúdo desses sites é copiado.
