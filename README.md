# funds
Web application to manage mutual funds.

Entities:
 - Users (Oid, Name, Password)
 - Assets (Oid, AssetType, AssetId, Description)
 - Accounts (Oid, Name, AccountType, UserOid)
 - Holdings (Oid, AccountOid, AssetOid, Amount)
 - Entries (Oid, TxnOid, Date, Amount, SourceOid, HoldingOid)
 - Transactions (Oid, TxnId, TxnType, Date, Amount, UserOid)
 - SourceDests (Oid, UserOid, BankId, RoutingNumber, AssetType)
 
 Codes
  - AssetType (Cash, Security)
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
      - AddSourceDest
      - ViewPortfolio
      - CloseAccount
  - Transactions
      - InjectCash
      - ExtractCash
      - BuyAssetWithCash
      - SellAssetForCash
      
BusinessRules:
 - Cash is just a particular type of asset, and AssetId is the currency code
 - 
