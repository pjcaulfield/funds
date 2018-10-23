# funds
Web application to manage mutual funds.

Entities:
 - Users (Oid, UserName <--, Password)
 - Assets (Oid, AssetId <--, Description)
 - Accounts (Oid, *UserOid, Name, AccountType, CashBalance)
 - SecHoldings (Oid, *AccountOid, *AssetOid, AssetBalance)
 - CashEntries (Oid, TxnOid, Date, Amount, *ExtCashAcctOid, *AccountOid)
 - SecEntries (Oid, TxnOid, Date, *SecHoldingOid, AssetAmount)
 - Transactions (Oid, TxnId <--, TxnType, Date, UserName, AccountName, CashAmount, AssetId, AssetAmount, ExtCashAcctShortName)
 - ExtCashAccts (Oid, *UserOid, BankId, RoutingNumber)
 
 Codes
  - AccountType (BeforeTax, AfterTax)
  - TxnType (InjectCash, ExtractCash, BuyAssetWithCash, SellAssetForCash)
 
 Use Cases:
  - Admin
      - SignUpUser
      - AddAsset
      - ReportUsers
      - ReportAssets
      - ReportTransactions
  - User
      - OpenAccount
      - AddExtCashAcct
      - ViewPortfolio
  - Transactions
      - InjectCash
      - ExtractCash
      - BuyAssetWithCash
      - SellAssetForCash
      
BusinessRules:
 - Only one currency is in use for the whole system
 - For a given account, only one asset of a given type can be held
