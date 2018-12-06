---
title: Tenant パラメーターを使用するコマンドレット
TOCTitle: Tenant パラメーターを使用するコマンドレット
ms:assetid: e7fe7c12-fbe0-49c1-9e8c-eef6958f27d0
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Dn362850(v=OCS.15)
ms:contentKeyID: 56270155
ms.date: 06/02/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Tenant パラメーターを使用するコマンドレット

 

_**トピックの最終更新日:** 2015-06-22_

パブリック プロバイダーの設定を変更する場合は、必ずテナント ID の入力が必要です。これはテナントが 1 つの場合でも同じです。たとえば、次のコマンドを実行すると Windows Live が通信できる唯一のパブリック プロバイダーになります。

    Set-CsTenantPublicProvider -Tenant "bf19b7db-6960-41e5-a139-2aa373474354" -Provider "WindowsLive"

ただし、これらのコマンドレットを実行するたびにテナント ID (bf19b7db-6960-41e5-a139-2aa373474354 など) を入力する必要はありません。代わりに、[Get-CsTenant](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsTenant) コマンドレットを実行してテナント ID を変数に保存し、他のコマンドレットの 1 つを呼び出す際にこの変数を使用すると、テナント ID を取得できます。次に例を示します。

    $x = (Get-CsTenant).TenantId
    Set-CsTenantPublicProvider -Tenant $x -Provider "WindowsLive"

または、テナント ID を取得してその値を Set-CsTenantPublicProvider コマンドレットにパイプ処理すると、この操作を 1 つのコマンドで実行できます。

    Get-CsTenant | Select-Object TenantId | ForEach-Object {Set-CsTenantPublicProvider -Tenant $_.TenantId -Provider "WindowsLive"}

**Get-CsTenant** コマンドレットを呼び出す際にテナント ID を指定する必要はありません。このコマンドを実行すると、テナントに関する情報が返されます。

    Get-CsTenant

次のコマンドレットではテナント ID を使用できます。ただしこの場合、パラメーターはオプションで、コマンドレットを呼び出す際に入力する必要はありません。Windows PowerShell では代わりに、現在接続している Skype for Business Online テナントに基づいてテナント ID が効率的に入力されます。

  - [Get-CsTenant](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsTenant)

  - [Set-CsTenantFederationConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsTenantFederationConfiguration)

  - [Set-CsTenantHybridConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsTenantHybridConfiguration)

  - [Get-CsTenantFederationConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsTenantFederationConfiguration)

  - [Get-CsTenantHybridConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsTenantHybridConfiguration)

  - [Get-CsTenantLicensingConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsTenantLicensingConfiguration)

たとえば、次のコマンドを使用して **Get-CsTenantFederationConfiguration** コマンドレットを呼び出すことができます。

    Get-CsTenantFederationConfiguration

Get-CsTenantFederationConfiguration を呼び出す際には、必須ではありませんが Tenant パラメーターを含めることができます。

    Get-CsTenantFederationConfiguration -Tenant "bf19b7db-6960-41e5-a139-2aa373474354"

## 関連項目

#### 概念

[ID、スコープ、およびテナント](identities-scopes-and-tenants-in-skype-for-business-online.md)  
[Lync Online のコマンドレット](https://docs.microsoft.com/en-us/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

