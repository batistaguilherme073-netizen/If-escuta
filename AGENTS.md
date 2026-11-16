<!-- LOVABLE:BEGIN -->
> [!IMPORTANT]
> This project is connected to [Lovable](https://lovable.dev). Avoid rewriting
> published git history — force pushing, or rebasing/amending/squashing commits
> that are already pushed — as it rewrites history on Lovable's side and the
> user will likely lose their project history.
>
> Commits you push to the connected branch sync back to Lovable and show up in
> the editor, so keep the branch in a working state.
<!-- LOVABLE:END -->

- Agenda events persist `pendente`, `realizado`, or `concluido`; `em atraso` is derived from a past pending date to avoid conflicting stored states.
- Weekly routine data is stored per user in browser storage, while agenda commitments remain sourced from the database.
- The offline service worker is registered only on the published site and never caches dev modules; the preview unregisters it to avoid stale mixed React copies.
- Coloring uses accessible, enclosed SVG regions with semantic pigment tokens and per-user browser storage so touch painting stays responsive without uploading artwork.
- The database coloring catalog is authoritative; built-in keys preserve existing paintings, while uploaded SVGs are reduced to allowlisted shapes and never rendered as raw HTML.
- Registration approval lives in an admin-controlled table; the root outlet gates the entire authenticated subtree without changing the managed auth layout, and restrictive RLS protects application data while allowing identity and approval-status reads. Admins retain review access.
- Circle participant reads use the security-definer membership helper rather than a self-referencing policy to prevent recursive RLS failures; both meeting modes share the same membership-gated chat.
