# funds
Web application to manage mutual fund information for users (does not include trading).

Entities and attributes:
 - Users (Oid, UserName (GU), Password (A))
 - Assets (Oid, AssetId (GU), Description (A))
 - Accounts (Oid, UserOid (O), AccountName (UO), AccountType (A), CashBalance (DA))
 - SecHoldings (Oid, AccountOid (O), AssetOid (R), AssetBalance (DA))
 - CashEntries (Oid, TxnOid (O), ExtCashAcctOid (R), AccountOid (R), PostingDate (A), CashAmount (A))
 - SecEntries (Oid, TxnOid (O), SecHoldingOid (R), PostingDate (A), AssetAmount (A))
 - Transactions (Oid, TxnId (GU), UserOid (R), TxnType (A), Date (A), UserName (A), AccountName (A), CashAmount (A), AssetId (A), AssetAmount (A), ExtCashAcctShortName (A))
 - ExtCashAccts (Oid, UserOid (O), ShortName (UO), BankId (A), RoutingNumber (A))
 
 Annotations for entities and attributes
  - O (owner), GU (globally unique), UO (unique within owner), A (attribute), DA (dynamic attribute), R (reference)
  
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
