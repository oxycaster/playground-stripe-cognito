# playground-stripe-cognito

CognitoとStripeの組み合わせで、最小構成のユーザー登録・認証・課金の仕組みを作る


サービスを作る場合、往々にして発生するのが

- SignUp
- SignIn

の仕組みであり、これらをサーバーレスで行いたい

AWSのサービスに [Cognito](https://aws.amazon.com/jp/cognito/) というサービスがあり

- Cognito
  - IdentityPool (AWSサービスへの認可)
  - UserPool (ユーザーのEmailやログインIDやPasswordなどの情報を管理し認証を行う)

という2つの役割の異なるサービスが提供されている


また、ユーザー登録完了時からサブスクリプション課金が発生し
サービス上のなんらかの機能を使うごとに都度課金が発生するといったモデルを想定する
このあたりの課金の仕組みは [Stripe](https://stripe.com/jp) を使用する
