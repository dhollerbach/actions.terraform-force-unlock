# Terraform Force Unlock

GitHub action that retrieves a Terraform LockID from DynamoDB and runs `terraform force-unlock`.

## Inputs

| Name          | Required     | Description                            |
| ------------- | ------------ | -------------------------------------- |
| `table_name`  | **Required** | DynamoDB table name for the lock.      |
| `lock_id_key` | **Required** | Lock ID key to retrieve from DynamoDB. |

## Example Usage

```yaml
- name: Configure AWS Credentials
  uses: aws-actions/configure-aws-credentials@v4
  with:
    aws-region: us-east-1
    role-to-assume: ${{ secrets.AWS_ROLE_ARN }}

- name: Terraform Force Unlock
  uses: dhollerbach/actions.terraform-force-unlock@v1
  with:
    table_name: my-dynamodb-table
    lock_id_key: my-lock-id-key
```
