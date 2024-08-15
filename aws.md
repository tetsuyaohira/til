## AWS CLIやSDKの認証情報の参照順
- 環境変数
  - `AWS_ACCESS_KEY_ID`, `AWS_SECRET_ACCESS_KEY`が設定されている場合はそれを使用
- Shared Credentials
  - `~/.aws/credentials`に設定されている場合はそれを使用
- AWS CLI設定ファイル
  - `~/.aws/config`に設定されている場合はそれを使用
- IAMロール
  - EC2の場合は、インスタンスに付与されたIAMロールを使用
  - ECSの場合は、ECSタスクロールを使用