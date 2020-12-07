# lint_lsp

`lint_lsp` is a tool to test linked changes to
`https://github.com/lsst-sqre/charts` and
`https://github.com/lsst-sqre/lsp-deploy`.

Its theory of operation is that it applies an environment-specific
values file to generate template-substituted YAML files from LSP helm
charts, and then submits those files via `kubectl` to a target cluster,
with `--dry-run=server` enabled so that it doesn't *actually* perform
any creations/deletions against your cluster.

It relies on three preconditions:

- you have the version of charts you want checked out somewhere
- you have the version of lsp-deploy you want checked out too
- you have kubectl using a kubeconfig pointing to the cluster you want
  to test against.
  

