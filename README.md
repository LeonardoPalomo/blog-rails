Tried to deploy this repository on railway.app

Built using a dockerfile

Got errors related to a missing secret key, so i followed this article: https://paulotijero.dev/articles/deploying-rails-api-in-railway/
  - Wrote on console "EDITOR='code --wait' rails credentials:edit" to get the secret key
  - Added secret key on the railway service:
    -Variables>RAW Editor>JSON {"SECRET_KEY_BASE":"<secret key from previous step>"}

It deploys fine, but can't save anything on the database because rails app come with sqlite3 as default, and that is not good for production. My suggestion is to start a new rails app with "rails new <app-name> -d=postgresql"

Update: This deployed fine on Render (render.com).