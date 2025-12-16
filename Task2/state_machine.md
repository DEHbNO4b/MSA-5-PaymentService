| Исходное состояние        | Переходное состояние          | Событие                                              |
|---------------------------|-------------------------------|------------------------------------------------------|
| INIT                      | PAYMENT_CREATED               | CREATE_PAYMENT                                       |
| PAYMENT_CREATED           | FUNDS_DEBITED                 | DEBIT_FUNDS_SUCCESS                                  |
| PAYMENT_CREATED           | FAILED                        | DEBIT_FUNDS_FAILED                                   |
| FUNDS_DEBITED             | FRAUD_CHECK_IN_PROGRESS       | START_FRAUD_CHECK                                    |
| FRAUD_CHECK_IN_PROGRESS   | APPROVED                      | FRAUD_ALLOW                                          |
| FRAUD_CHECK_IN_PROGRESS   | MANUAL_REVIEW_PENDING         | FRAUD_MANUAL_REVIEW                                  |
| FRAUD_CHECK_IN_PROGRESS   | DECLINED                      | FRAUD_DENY                                           |
| MANUAL_REVIEW_PENDING     | APPROVED                      | MANUAL_REVIEW_APPROVE                                |
| MANUAL_REVIEW_PENDING     | DECLINED                      | MANUAL_REVIEW_DENY                                   |
| MANUAL_REVIEW_PENDING     | APPROVED                      | CUTOFF_TIMEOUT_EXPIRED                               |
| DECLINED                  | REFUND_IN_PROGRESS            | BLOCK_PAYMENT                                        |
| REFUND_IN_PROGRESS        | REFUNDED                      | REFUND_FUNDS_SUCCESS                                 |
| REFUNDED                  | NOTIFIED_FAILURE              | SEND_NOTIFICATION                                    |
| DECLINED                  | SECURITY_NOTIFIED             | NOTIFY_SECURITY                                      |
| APPROVED                  | MERCHANT_CREDITED             | CREDIT_MERCHANT                                      |
| MERCHANT_CREDITED         | NOTIFIED_SUCCESS              | SEND_NOTIFICATION                                    |
| NOTIFIED_SUCCESS          | COMPLETED                     | COMPLETE_PAYMENT                                     |
