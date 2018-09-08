---
title: ビジネス オンラインの Skype に、オンプレミスのユーザーを移動します。
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 1/27/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 2475674a-f592-4fa8-ae99-f71cbea54dc0
description: '概要: 移動の詳細について設置 Skype ユーザー ビジネスをオンラインにします。'
ms.openlocfilehash: 1cb57e777b9353b1abb5b211563f5b6adc58e72c
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2018
ms.locfileid: "23882069"
---
# <a name="move-on-premises-users-to-skype-for-business-online"></a>ビジネス オンラインの Skype に、オンプレミスのユーザーを移動します。
 
**の概要:** ビジネス オンラインの Skype をオンプレミス ユーザーの移動について説明します。
  
> [!CAUTION]
> オンプレミス環境で Skype for Business Online に移動する前に、Lync Phone Edition デバイスを最小要求ファームウェアに更新する必要があります。 オンプレミスからオンラインにユーザーを移動してからファームウェアを更新すると、ユーザーは電話を使用して接続できなくなります。 この問題を訂正するには、ユーザーをオンプレミス環境に戻して、電話を最小ファームウェアに更新する必要があります。 最小ファームウェアに更新するか、電話をハード リセットしてから、ユーザーをオンプレミス環境に戻すことは試みないでください。
デバイスが最小ファームウェアになっていないときにハード リセットを実行すると、既定で PIN 認証を使用するようになります。これは、Skype for Business Online でサポートされていません。 詳細については、[オンライン ビジネスの Skype の電話を取得する](https://support.office.com/en-us/article/Getting-phones-for-Skype-for-Business-Online-91f2d947-45fc-4fab-bd8b-2e313531c477?ui=en-US&amp;rs=en-US&amp;ad=US)を参照してください。
  
これは、オンライン ビジネスの Skype に、オンプレミスのユーザーを移動する場合にのみ要求されるオプションの手順です。 Skype をビジネス オンラインのユーザーを移動する作業を開始する前に、ビジネス オンライン コネクタ (Windows PowerShell モジュール) の Skype がフロント エンド サーバーで運用されていることを確認します。 、いない場合は、[ダウンロード センター](https://www.microsoft.com/en-us/download/details.aspx?id=39366)からダウンロードできます。 また、AD を準備するには Azure AD Connect の構成が必要です。 1.0.9125.0 以降のバージョンの AAD Connect を使用する必要があります。 それよりも前のバージョンの AAD Connect ツールまたは DirSync を使用している場合は、サポートされているバージョンにアップグレードしてください。 現在のインストールをアップグレードして、環境で定義しているカスタム ルールを維持できます。
  
使用していずれかの Skype ビジネス サーバーのコントロール パネルまたは Skype のビジネス サーバー管理シェルの設置型展開でユーザーを移動するが、Office 365 の展開の管理者の資格情報を持つ必要があります。
  
## <a name="moving-users-by-using-skype-for-business-control-panel"></a>ビジネス コントロール パネルの Skype を使用して、ユーザーの移動

### <a name="to-move-a-user-to-skype-for-business-online"></a>Skype をビジネス オンラインのユーザーを移動するには

1. CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウント、コンピューターにログオンする、ビジネス サーバー、または Skype を内部展開で最小の Skype ビジネス サーバー管理ツールがインストールされているのです。
    
2. [スタート] メニューまたはデスクトップのショートカットでは、ビジネス サーバーのコントロール パネルの Skype を開きます。
    
    Skype は、1 つを構成した場合は、管理者の URL を使用してビジネス サーバーのコントロール パネルにもアクセスできます。
    
3. 左側のナビゲーション バーで [**ユーザー**] をクリックします。
    
4. [**ユーザーの検索**] ボックスに、有効にするユーザー アカウントの表示名、名、姓、セキュリティ アカウント マネージャー (SAM) のアカウント名、SIP アドレス、または回線 URI (Uniform Resource Identifier) の全体か先頭の部分の文字列を入力して、[**検索**] をクリックします。
    
5. ユーザーをクリックし、[**アクション**] メニューで [**選んだユーザーを Skype for Business Online に移動**] をクリックします。
    
6. [**選択したユーザーを Skype for Business Online に移動**] ページの情報を確認して、[**次へ**] をクリックします。
    
7. 次のページでは、するは、まだ署名されていない場合 Office 365 に、 **Office 365 にサインイン**] をクリックして、資格情報を入力、 **[ok]** および [**次へ**] をクリックします。
    
8. 移動するユーザー数が正しいことを確認して、[**次へ**] をクリックします。
    
9. 次のページで結果を確認して、[**閉じる**] をクリックします。
    
## <a name="moving-users-by-using-skype-for-business-server-management-shell"></a>Skype ビジネス サーバー管理シェルを使用してユーザーの移動

オンライン ビジネスのテナントの Skype に、オンプレミスのユーザーを移動するには、ビジネス サーバー管理シェルを管理者の資格情報を使用して、Microsoft Office 365 のテナントのため、Skype で次のコマンドレットを実行します。 "username@contoso.com" を、移動するユーザーの情報で置換します。
  
```
$creds=Get-Credential
```

```
Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -Credential $creds -HostedMigrationOverrideUrl <URL>
```

**HostedMigrationOverrideUrl**パラメーターは次の形式で、ホストの移行サービスが実行されているプールへの URL である必要があります用に指定された URL の形式: _Https://\<プールの FQDN\>/HostedMigration/hostedmigrationService.svc_。
  
Office 365 テナント アカウントのビジネスのオンライン管理センターの Skype の URL を表示することによってホストされている移行サービスの URL を指定できます。
  
> [!NOTE]
> この URL では大文字と小文字が区別されます。 
  
### <a name="to-determine-the-hosted-migration-service-url-for-your-office-365-tenant"></a>Office 365 テナントのホスティング型移行サービスの URL を確認するには

1. 管理者として Office 365 テナントにログインします。
    
2. [**Skype for Business 管理センター**] を開きます。
    
3. [**Skype for Business 管理センター**] が表示されたら、**lync.com** の近くのアドレス バーの URL を選択してコピーします。URL は、次のような書式です。
    
     `https://webdir0a.online.lync.com/lscp/?language=en-US&amp;tenantID=`
    
4. URL の **webdir** を **admin** に置き換えると、次のようになります。 
    
     `https://admin0a.online.lync.com`
    
5. URL に以下の文字列を付加します。**/HostedMigration/hostedmigrationservice.svc**
    
    結果の URL は、 **HostedMigrationOverrideUrl**の値は、次のようになります。
    
     `https://admin0a.online.lync.com/HostedMigration/hostedmigrationService.svc`
    

