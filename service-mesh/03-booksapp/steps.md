### Install the booksapp

    kubectl create ns booksapp && curl -sL https://run.linkerd.io/booksapp.yml  | kubectl -n booksapp apply -f -

### Inject linkerd

    kubectl get -n booksapp deploy -o yaml | linkerd inject - | kubectl apply -f -

### generate the Service Profile CRD (already generated)

    curl -sL https://run.linkerd.io/booksapp/webapp.swagger \
        | linkerd -n booksapp profile --open-api - webapp \
        | kubectl -n booksapp apply -f -

    curl -sL https://run.linkerd.io/booksapp/authors.swagger \
        | linkerd -n booksapp profile --open-api - authors \
        | kubectl -n booksapp apply -f -

    curl -sL https://run.linkerd.io/booksapp/books.swagger \
        | linkerd -n booksapp profile --open-api - books \
        | kubectl -n booksapp apply -f -

### Apply Service Routes

    kubectl apply -f authors-profile.yaml
    kubectl apply -f books-profile.yaml
    kubectl apply -f webapp-profile.yaml
