# JackAI Platform OS Hub API (public subset) Go API

<!-- omniwrap-api-reference eyJjb250cmFjdF9maW5nZXJwcmludCI6ImM3Y2E1ZTVlYmI0YzA5MjkxMGVjNzJiMzcxZTE4ODMwMzM1OGM1ZTM0ZDI5MDhjMGE4OGY3ODJhMjQxMTYyY2YiLCJvcGVyYXRpb25fY291bnQiOjgsInJlbmRlcmVyIjoiZ28iLCJ2ZXJzaW9uIjoiMS41LjAifQ -->

This generated index is tied to Semantic IR `1.14.0` and contract fingerprint `c7ca5e5ebb4c092910ec72b371e188303358c5e34d2908c0a88f782a241162cf`. Every operation below is rendered from the same semantic contract and artifact-attested public member allocation as the SDK.

SDK maturity: **experimental**  
Artifact evidence: [`omniwrap-artifact.json`](omniwrap-artifact.json) binds this file by SHA-256 and is revalidated by the package gate.

## Client hooks and tracing

`option.WithHooks(option.Hooks{...})` registers four callbacks. Every attempt starts with `BeforeRequest` and ends with exactly one of `OnRetry` (another attempt follows), `AfterResponse` (the success the call returns) or `OnError` (the failure the call reports). Each receives the operation id, the HTTP method, the URL, the request headers, the attempt number (from 1), the time elapsed since the call started and, once the server answered, the HTTP status. No context carries a credential: `Authorization`, `Proxy-Authorization`, `Cookie`, every API-key header and API-key query parameter, and any configured credential value read `[redacted]`. Every hook receives an `option.HookContext` value holding copies: no hook can change the request.

`option.WithTracer(tracer)` opens one span per call through the tracer interface this SDK defines, named after the operation id, with `http.request.method`, `http.response.status_code` and `http.request.resend_count`. It needs no tracing library; README.md maps it onto the OpenTelemetry API.

## Resource `Health`

<!-- omniwrap-api-operation eyJleGFtcGxlX3JlYXNvbiI6bnVsbCwiZXhhbXBsZV9zdGF0dXMiOiJnZW5lcmF0ZWQiLCJtZW1iZXIiOiJIZWFsdGguR2V0IiwibWV0aG9kIjoiR0VUIiwib3BlcmF0aW9uX2lkIjoiZ2V0SGVhbHRoIiwicGF0aCI6Ii9oZWFsdGgiLCJyZXNvdXJjZSI6IkhlYWx0aCIsInNlY3Rpb25fc2hhMjU2IjoiZDM5NGUyODQzMzE2MmQ2NjM4ZTQwZTZmOTdmNmRkNmQ3NjAxODI0NTkyMWJjNTRlMzNjNGNhNWUxNzRjZWQyNyIsInNpZ25hdHVyZV9zaGEyNTYiOiI1ODM5MzRjNzRkMDNhYTEzYjg5MDMyMDU1MmYxZjhmODc1MGE4YWU4YWEyMzc0MzdkY2Y2MWMzOGJkZDYzYmM2In0 -->
### `client.Health.Get`

Operation ID: `getHealth`  
Route: `GET` `/health`  

#### Signature

```go
func (service *HealthService) Get(ctx context.Context, params HealthGetParams, opts ...option.RequestOption) (*Response[JSONValue], error)
```

#### Parameters

| Name | In | Required | Contract type | Description |
| --- | --- | --- | --- | --- |
| _none_ | | | | |

#### Responses

| Status | Description | Content |
| --- | --- | --- |
| `200` | Hub liveness status | none |

#### Canonical required-input example

```json
{
  "parameters": []
}
```

#### SDK call example

Example status: `generated`  
```go
result, err := client.Health.Get(ctx)
```

<!-- omniwrap-api-operation-end eyJvcGVyYXRpb25faWQiOiJnZXRIZWFsdGgifQ -->

## Resource `User`

<!-- omniwrap-api-operation eyJleGFtcGxlX3JlYXNvbiI6bnVsbCwiZXhhbXBsZV9zdGF0dXMiOiJnZW5lcmF0ZWQiLCJtZW1iZXIiOiJVc2VyLkdldEN1cnJlbnQiLCJtZXRob2QiOiJHRVQiLCJvcGVyYXRpb25faWQiOiJnZXRDdXJyZW50VXNlciIsInBhdGgiOiIvdXNlci9tZSIsInJlc291cmNlIjoiVXNlciIsInNlY3Rpb25fc2hhMjU2IjoiYTQ1YjRiYjUxMjAzM2Q1MWI2MWVhNTdjMzFhZWU3NGI0NDU1NTVjMjAxNDg0YTcyNzY4Nzg3Yzc4MmFmNDUyZiIsInNpZ25hdHVyZV9zaGEyNTYiOiI5ZmI5NDJjYjY1MmUzNGQ3OWExZDIyYjE4YjlhNDM1NGZlOTlkN2NlZTI4YTI1NDJlZjgwZTA4YmNlZDFhZjUwIn0 -->
### `client.User.GetCurrent`

Operation ID: `getCurrentUser`  
Route: `GET` `/user/me`  

#### Signature

```go
func (service *UserService) GetCurrent(ctx context.Context, params UserGetCurrentParams, opts ...option.RequestOption) (*Response[JSONValue], error)
```

#### Parameters

| Name | In | Required | Contract type | Description |
| --- | --- | --- | --- | --- |
| _none_ | | | | |

#### Responses

| Status | Description | Content |
| --- | --- | --- |
| `200` | Current user context | none |

#### Canonical required-input example

```json
{
  "parameters": []
}
```

#### SDK call example

Example status: `generated`  
```go
result, err := client.User.GetCurrent(ctx)
```

<!-- omniwrap-api-operation-end eyJvcGVyYXRpb25faWQiOiJnZXRDdXJyZW50VXNlciJ9 -->

<!-- omniwrap-api-operation eyJleGFtcGxlX3JlYXNvbiI6bnVsbCwiZXhhbXBsZV9zdGF0dXMiOiJnZW5lcmF0ZWQiLCJtZW1iZXIiOiJVc2VyLkdldFNpZ251cFBvbGljeSIsIm1ldGhvZCI6IkdFVCIsIm9wZXJhdGlvbl9pZCI6ImdldFNpZ251cFBvbGljeSIsInBhdGgiOiIvdXNlci9hdXRoL3NpZ251cC1wb2xpY3kiLCJyZXNvdXJjZSI6IlVzZXIiLCJzZWN0aW9uX3NoYTI1NiI6IjkwM2RiNjBiZTU4ODZiZGRjNDVmMTM5ZWE0ZDFhZmEzYzI3OWE2Mzc0YjkxZGNhMzljYmMyNzJhOGYzMTMwZmUiLCJzaWduYXR1cmVfc2hhMjU2IjoiZmVkNGZhNjIwODAxNmI0OTI5Yzk4MDEwMDE0ODBmYTk1ZDJmZGE5MzVkZjM0ZWRiYjA4YWE1NjQwOWU3ZTAwMyJ9 -->
### `client.User.GetSignupPolicy`

Operation ID: `getSignupPolicy`  
Route: `GET` `/user/auth/signup-policy`  

#### Signature

```go
func (service *UserService) GetSignupPolicy(ctx context.Context, params UserGetSignupPolicyParams, opts ...option.RequestOption) (*Response[JSONValue], error)
```

#### Parameters

| Name | In | Required | Contract type | Description |
| --- | --- | --- | --- | --- |
| _none_ | | | | |

#### Responses

| Status | Description | Content |
| --- | --- | --- |
| `200` | Current signup policy | none |

#### Canonical required-input example

```json
{
  "parameters": []
}
```

#### SDK call example

Example status: `generated`  
```go
result, err := client.User.GetSignupPolicy(ctx)
```

<!-- omniwrap-api-operation-end eyJvcGVyYXRpb25faWQiOiJnZXRTaWdudXBQb2xpY3kifQ -->

<!-- omniwrap-api-operation eyJleGFtcGxlX3JlYXNvbiI6bnVsbCwiZXhhbXBsZV9zdGF0dXMiOiJnZW5lcmF0ZWQiLCJtZW1iZXIiOiJVc2VyLkxvZ2luIiwibWV0aG9kIjoiUE9TVCIsIm9wZXJhdGlvbl9pZCI6ImxvZ2luVXNlciIsInBhdGgiOiIvdXNlci9hdXRoL2xvZ2luIiwicmVzb3VyY2UiOiJVc2VyIiwic2VjdGlvbl9zaGEyNTYiOiJiOWI4NzU0Nzg1OTkwOTMwNzUzODgzNGI1ZjJjY2UyMjM3ZjdhYTcyZWQxNGQwMjQ2NzgwY2EyMGI4NjkzOWE0Iiwic2lnbmF0dXJlX3NoYTI1NiI6ImViZTM5ZTE3YjUwMzg1NGFmYWE0Nzc3NTJjMWExN2RhYTM5NzBiNjM3Y2YxNWQ4NDM2NGZmMzk0MzI2NDJiMzIifQ -->
### `client.User.Login`

Operation ID: `loginUser`  
Route: `POST` `/user/auth/login`  

#### Signature

```go
func (service *UserService) Login(ctx context.Context, params UserLoginParams, opts ...option.RequestOption) (*Response[JSONValue], error)
```

#### Parameters

| Name | In | Required | Contract type | Description |
| --- | --- | --- | --- | --- |
| _none_ | | | | |

#### Responses

| Status | Description | Content |
| --- | --- | --- |
| `200` | Authenticated session or MFA challenge | none |

#### Canonical required-input example

```json
{
  "parameters": []
}
```

#### SDK call example

Example status: `generated`  
```go
result, err := client.User.Login(ctx)
```

<!-- omniwrap-api-operation-end eyJvcGVyYXRpb25faWQiOiJsb2dpblVzZXIifQ -->

<!-- omniwrap-api-operation eyJleGFtcGxlX3JlYXNvbiI6bnVsbCwiZXhhbXBsZV9zdGF0dXMiOiJnZW5lcmF0ZWQiLCJtZW1iZXIiOiJVc2VyLlN1Ym1pdFdhaXRsaXN0UmVxdWVzdCIsIm1ldGhvZCI6IlBPU1QiLCJvcGVyYXRpb25faWQiOiJzdWJtaXRXYWl0bGlzdFJlcXVlc3QiLCJwYXRoIjoiL3VzZXIvYXV0aC93YWl0bGlzdCIsInJlc291cmNlIjoiVXNlciIsInNlY3Rpb25fc2hhMjU2IjoiOGMyYjM3NTVlNjVkZGZkYmM0NjcyMDllZjliMjdmY2ZiNWVkYTY2Y2FkNWE1ZGE1NWYxYTAyYWZiNzJmMWFjZSIsInNpZ25hdHVyZV9zaGEyNTYiOiIwNTNjNjI2NGVmZGI5MjQwZDBjZmVmZDQ0Y2VmMmJiMTNjMGZlYTI4NTk5MTI4N2JmNDNkODJiNDhlODFmOTdmIn0 -->
### `client.User.SubmitWaitlistRequest`

Operation ID: `submitWaitlistRequest`  
Route: `POST` `/user/auth/waitlist`  

#### Signature

```go
func (service *UserService) SubmitWaitlistRequest(ctx context.Context, params UserSubmitWaitlistRequestParams, opts ...option.RequestOption) (*Response[JSONValue], error)
```

#### Parameters

| Name | In | Required | Contract type | Description |
| --- | --- | --- | --- | --- |
| _none_ | | | | |

#### Responses

| Status | Description | Content |
| --- | --- | --- |
| `202` | Waitlist request recorded with an opaque WL- reference | none |

#### Canonical required-input example

```json
{
  "parameters": []
}
```

#### SDK call example

Example status: `generated`  
```go
result, err := client.User.SubmitWaitlistRequest(ctx)
```

<!-- omniwrap-api-operation-end eyJvcGVyYXRpb25faWQiOiJzdWJtaXRXYWl0bGlzdFJlcXVlc3QifQ -->

## Resource `V1`

<!-- omniwrap-api-operation eyJleGFtcGxlX3JlYXNvbiI6bnVsbCwiZXhhbXBsZV9zdGF0dXMiOiJnZW5lcmF0ZWQiLCJtZW1iZXIiOiJWMS5GYWlsVXNhZ2VRdW90YSIsIm1ldGhvZCI6IlBPU1QiLCJvcGVyYXRpb25faWQiOiJmYWlsVXNhZ2VRdW90YSIsInBhdGgiOiIvdjEva2VybmVsL3VzYWdlL2ZhaWwiLCJyZXNvdXJjZSI6IlYxIiwic2VjdGlvbl9zaGEyNTYiOiIwYmExNDgyYjg3ZjU1MThlNTU1ZDNmZmMxMDcyMTUzYjU5NmQ0NTkwYmM2ODAwYzY0YzE2OTg2NjJkOWU1OGEzIiwic2lnbmF0dXJlX3NoYTI1NiI6IjUxN2YwZGY4ZTU2NGIzYzEwZGMxNjJhODg2NjNiYTdmNTI4OTVhZDA3OTdhNWJmNDA0MDE1YmMzYzM3MTI1ZTcifQ -->
### `client.V1.FailUsageQuota`

Operation ID: `failUsageQuota`  
Route: `POST` `/v1/kernel/usage/fail`  

#### Signature

```go
func (service *V1Service) FailUsageQuota(ctx context.Context, params V1FailUsageQuotaParams, opts ...option.RequestOption) (*Response[JSONValue], error)
```

#### Parameters

| Name | In | Required | Contract type | Description |
| --- | --- | --- | --- | --- |
| _none_ | | | | |

#### Responses

| Status | Description | Content |
| --- | --- | --- |
| `200` | Reservation released | none |

#### Canonical required-input example

```json
{
  "parameters": []
}
```

#### SDK call example

Example status: `generated`  
```go
result, err := client.V1.FailUsageQuota(ctx)
```

<!-- omniwrap-api-operation-end eyJvcGVyYXRpb25faWQiOiJmYWlsVXNhZ2VRdW90YSJ9 -->

<!-- omniwrap-api-operation eyJleGFtcGxlX3JlYXNvbiI6bnVsbCwiZXhhbXBsZV9zdGF0dXMiOiJnZW5lcmF0ZWQiLCJtZW1iZXIiOiJWMS5GaW5hbGl6ZVVzYWdlUXVvdGEiLCJtZXRob2QiOiJQT1NUIiwib3BlcmF0aW9uX2lkIjoiZmluYWxpemVVc2FnZVF1b3RhIiwicGF0aCI6Ii92MS9rZXJuZWwvdXNhZ2UvZmluYWxpemUiLCJyZXNvdXJjZSI6IlYxIiwic2VjdGlvbl9zaGEyNTYiOiIzODQyNjA4MGExNzllMzE3NzM4YTkzOTkwMjMwNzdmMjI1NWQ0NzBlYWRmODg5MWQwYmQ2MWEyZDUxYjZiYjQzIiwic2lnbmF0dXJlX3NoYTI1NiI6ImIxZGYyN2IyYjdiNGNjMGE4NjQxODU5NTkzMGI2N2UxMjNlNjI0ZmVmNDk3NWExMmM4YzVmMjIxOTNjOTUzNmIifQ -->
### `client.V1.FinalizeUsageQuota`

Operation ID: `finalizeUsageQuota`  
Route: `POST` `/v1/kernel/usage/finalize`  

#### Signature

```go
func (service *V1Service) FinalizeUsageQuota(ctx context.Context, params V1FinalizeUsageQuotaParams, opts ...option.RequestOption) (*Response[JSONValue], error)
```

#### Parameters

| Name | In | Required | Contract type | Description |
| --- | --- | --- | --- | --- |
| _none_ | | | | |

#### Responses

| Status | Description | Content |
| --- | --- | --- |
| `200` | Reservation finalized | none |

#### Canonical required-input example

```json
{
  "parameters": []
}
```

#### SDK call example

Example status: `generated`  
```go
result, err := client.V1.FinalizeUsageQuota(ctx)
```

<!-- omniwrap-api-operation-end eyJvcGVyYXRpb25faWQiOiJmaW5hbGl6ZVVzYWdlUXVvdGEifQ -->

<!-- omniwrap-api-operation eyJleGFtcGxlX3JlYXNvbiI6bnVsbCwiZXhhbXBsZV9zdGF0dXMiOiJnZW5lcmF0ZWQiLCJtZW1iZXIiOiJWMS5SZXNlcnZlVXNhZ2VRdW90YSIsIm1ldGhvZCI6IlBPU1QiLCJvcGVyYXRpb25faWQiOiJyZXNlcnZlVXNhZ2VRdW90YSIsInBhdGgiOiIvdjEva2VybmVsL3VzYWdlL3Jlc2VydmUiLCJyZXNvdXJjZSI6IlYxIiwic2VjdGlvbl9zaGEyNTYiOiI0MGJkZmViNDA2ODAxNjk0OWU0MmQ2MmI0NzQ1YWVlOWI2MTQ2MjYxMzhlMzNlZWUxZTljMGQxOTdiMjNlYmJhIiwic2lnbmF0dXJlX3NoYTI1NiI6ImI2YWFmYzlhMzIyYzg3YjExZjM4MjVjYmE4ZGQzOWMyMWVkNWU5NThhY2E1YzVmZWRmYWZmYjJlY2VlY2U4NDgifQ -->
### `client.V1.ReserveUsageQuota`

Operation ID: `reserveUsageQuota`  
Route: `POST` `/v1/kernel/usage/reserve`  

#### Signature

```go
func (service *V1Service) ReserveUsageQuota(ctx context.Context, params V1ReserveUsageQuotaParams, opts ...option.RequestOption) (*Response[JSONValue], error)
```

#### Parameters

| Name | In | Required | Contract type | Description |
| --- | --- | --- | --- | --- |
| _none_ | | | | |

#### Responses

| Status | Description | Content |
| --- | --- | --- |
| `200` | Reservation lease created | none |

#### Canonical required-input example

```json
{
  "parameters": []
}
```

#### SDK call example

Example status: `generated`  
```go
result, err := client.V1.ReserveUsageQuota(ctx)
```

<!-- omniwrap-api-operation-end eyJvcGVyYXRpb25faWQiOiJyZXNlcnZlVXNhZ2VRdW90YSJ9 -->

