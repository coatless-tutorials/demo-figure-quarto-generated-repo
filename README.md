# Demo Quarto Generated Figures Repository

This repository stores generated figures for Quarto websites as a git submodule, keeping the main content repository lightweight and fast to clone.

## Repository Structure

```
├── post-figures/
│   └── welcome/
│       └── example-plot-1.png
└── README.md
```

## Usage

This repository is designed to be used as a git submodule in Quarto website projects. Figures are automatically generated here when Quarto documents are rendered with proper `fig.path` configuration.

### Integration Example

In your main repository's Quarto documents, place the following in the document YAML:

```yaml
knitr:
  opts_chunk:
    fig.path: ../../figures/post-figures/
```

### Manual Updates

If you need to commit new figures:

```bash
# In the figures directory of your main repo
cd figures
git add .
git commit -m "Add figures for new blog post"
git push origin main

# Back in main repo, update the submodule pointer
cd ..
git add figures
git commit -m "Update figures submodule"
git push origin main
```

## Related Repositories

- **Main Website**: [demo-figure-quarto-website](https://github.com/coatless-tutorials/demo-figure-quarto-website)
- **Implementation Guide**: [Stop Bloating Your Quarto Repository with Figure Files](https://blog.thecoatlessprofessor.com/programming/quarto/stop-bloating-your-main-quarto-website-repository-with-generated-figure-files/)

