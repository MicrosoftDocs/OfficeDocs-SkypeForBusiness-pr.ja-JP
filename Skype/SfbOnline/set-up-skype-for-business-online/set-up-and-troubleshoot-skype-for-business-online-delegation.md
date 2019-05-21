---
title: Skype for Business Online の代理のセットアップとトラブルシューティング
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: e676b911-5f82-41d8-b4ce-3d0d45c3cd04
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Setup
description: この記事では、Skype for Business Online の委任のセットアップとトラブルシューティングの方法について説明します。 この記事では、セットアップの推奨事項、ベストプラクティス、およびトラブルシューティングの手順に関するガイダンスを示します。
ms.openlocfilehash: 0528bbb3dc25e085d38f86c040eb5129c9d039c1
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34285246"
---
# <a name="set-up-and-troubleshoot-skype-for-business-online-delegation"></a>Skype for Business Online の代理のセットアップとトラブルシューティング

この記事では、Skype for Business Online の委任のセットアップとトラブルシューティングの方法について説明します。 この記事では、セットアップの推奨事項、ベストプラクティス、およびトラブルシューティングの手順に関するガイダンスを示します。
  
## <a name="guidelines-and-requirements"></a>ガイドラインと要件

### <a name="guidelines-for-delegation"></a>代理人のためのガイドライン

委任を正しく動作させるための設定と取得は、次のガイドラインに従うことによって異なります。
  
- 最新の更新プログラムまたは Skype for Business 2016 フルクライアントを使用して、Skype for Business 2015 フルクライアントを使用している必要があります。
    
- 最新の更新プログラムまたは Outlook 2016 クライアントで Outlook 2013 クライアントを使用している必要があります。
    
- 委任者および代理人のコンピューターに、プライマリまたは既定のプロファイルである Outlook メールプロファイルが1つ含まれていることを確認します。 このメールプロファイルには、アカウントが1つだけ含まれている必要があります。
    
- Skype for Business for 委任者と代理人は、オンラインユーザーである必要があります。 また、各アカウントの Exchange Server メールボックスは、両方ともオンラインであるか、両方ともオンプレミスである必要があります。
    
- 委任者と代理人の両方が、同じメジャーバージョンの Outlook を使用している必要があります。
    
- クライアントポリシーで**EnableExchangeDelegateSync**属性値が**true**に設定されている必要があります。 この設定を確認するには、Skype for Business Online PowerShell モジュールで、 **CSClientPolicy**コマンドレットを実行します。
    
- 委任者と代理人の両方が、異なるワークステーションで Skype for Business と Outlook を同時にサインインしている必要があります。
    
- 共有メールボックスは、Skype for Business Online の委任ではサポートされていません。 これは、共有メールボックスに**sendonbehalf**アクセス制御リスト (ACL) が含まれていないためです。
    
### <a name="skype-for-business-client-version-support"></a>Skype for Business クライアントのバージョンのサポート

||**Outlook 2013**|**Outlook 2016**|
|:-----|:-----|:-----|
|**Lync/Skype for Business Basic クライアント**| サポートされていない |サポートされていない
|**Skype for Business 2015**|サポート対象| サポート対象|
|**Skype for Business 2016**|サポート対象| サポート対象|

   
### <a name="licensing-requirements"></a>ライセンス要件

**Enterprise E3 ライセンスのシナリオ**

|**ライセンス**|**クライアント**|**メモ**|
|:-----|:-----|:-----|
|エンタープライズ E3  <br/> |Outlook 2013 または Outlook 2016 で使用されている Lync 2013 (Skype for Business 2015)  <br/> Outlook 2013 または Outlook 2016 で使用される Skype for Business 2016  <br/> |Skype for Business Basic クライアントは、委任をサポートしていません。  <br/> Mac クライアントでは、通話を委任することはできますが、会議を委任することはできません。  <br/> |
|Enterprise E3 と Office 365 電話システム + Office 365 xCalling プラン  <br/> |Outlook 2013 または Outlook 2016 で使用されている Lync 2013 (Skype for Business 2015)  <br/> Outlook 2013 または Outlook 2016 で使用される Skype for Business 2016  <br/> Lync for Mac 2011  <br/> |Skype for Business Basic クライアントは、委任をサポートしていません。  <br/> Mac クライアントでは、通話を委任することはできますが、会議を委任することはできません。  <br/> |
   
**Enterprise E5 ライセンスのシナリオ**

|**ライセンス**|**クライアント**|**メモ**|
|:-----|:-----|:-----|
|Enterprise E5  <br/> |Lync 2013 (Skype for Business 2015) は、Outlook 2013 または Outlook 2016 で使用されています。  <br/> Outlook 2013 または Outlook 2016 で使用される Skype for Business 2016  <br/> |Skype for Business Basic クライアントは、委任をサポートしていません。  <br/> Mac クライアントでは、通話を委任することはできますが、会議を委任することはできません。  <br/> |
|Enterprise E5 plus Office 365 通話プラン  <br/> |Skype for Business for Mac 2016  <br/> Outlook 2013 または Outlook 2016 で使用されている Lync 2013 (Skype for Business 2015)  <br/> Outlook 2013 または Outlook 2016 で使用される Skype for Business 2016  <br/> Lync for Mac 2011  <br/> |Skype for Business Basic クライアントは、委任をサポートしていません。  <br/> Mac クライアントでは、通話を委任することはできますが、会議を委任することはできません。  <br/> |
   
## <a name="set-up-and-verify-delegation"></a>委任を設定および確認する

Skype for Business Online の委任を設定するには、次の手順を実行します。
  
### <a name="for-windows-clients"></a>Windows クライアントの場合

 **[着信の転送] タブ**
  
1. [**ツール** > **]** > の [**着信の転送設定**] を選びます。
    
2. [**代理人メンバーの編集**] を選びます。
    
3. [**追加**] を選択し、追加する代理人を選択して、[ **OK]** を選択します。
    
 **[着信の転送] タブ**
  
1. Outlook で、[**ファイル** > **アカウント設定** > **** > ****] を選択します。
    
2. 代理人になるユーザーの名前を探して追加します。
    
3. [**予定表**] メニューを選択し、[**編集] (アイテムを参照、作成、変更できる)** を選択します。
    
### <a name="for-mac-clients---lync"></a>Mac クライアントの場合-Lync

 **[着信の転送] タブ**
  
- クライアントに **[代理人メンバーの編集**] リンクがある [**着信の転送**] タブがありません。また、委任者が Mac コンピューターにある場合、委任者は、委任を設定するために Windows ベースのコンピューターにサインインする必要があります。 これは、Mac クライアントが MAPI 接続を確立できないため、Skype for Business の委任を Outlook から確立するための要件です。
    
### <a name="verify-success"></a>成功を確認する

セットアップに成功した場合、代理人には、 **_LT_ Name> メッセージの代理人として追加され**たことと、グループ**の管理者を管理する相手**が作成されたことがわかります。 委任者には、**代理人**グループが作成されていることがわかります。
  
> [!NOTE]
> 委任権限は通常、セットアッププロセスで30分以内に表示されます。 ただし、このプロセスが完了するまでに最大24時間かかることがあります。 
  
## <a name="troubleshooting"></a>トラブルシューティング

### <a name="common-issues"></a>一般的な問題

- > **問題 1**委任者によって Outlook クライアントから代理人が削除された後、[グループ**の呼び出しを管理する人**] グループに代理人エントリが表示されたままになります。
    
  - > **解像度 1**Skype for Business クライアントで、[**代理人**] グループの代理人を右クリックし、[**グループから削除**] を選択します。
    
- > **問題 2**Outlook クライアントから代理人アクセス権が付与された後は、[確認メッセージ] と [**他の人として通話を管理**する] グループは代理人に対して表示されません。
    
  - > **解決方法 2**Outlook クライアントから委任を削除し、レプリケーションを15分ほど待ってから、もう一度代理人を追加します。
    
### <a name="other-common-issues"></a>その他の一般的な問題

- 委任が機能しないのは、最大でが25個と25個のデリゲートのしきい値を超えた場合です。
    
- Skype for Business Basic クライアントはサポートされていません。
    
    > [!NOTE]
    > Skype for Business Basic クライアントをインストールすると、委任が削除され、解除されます。 
  
- [ **MAPI Status** ] の値**が [OK]** になっていない場合は、 **SIP**と**SMTP**の値が一致していることを確認します。
    
    > [!NOTE]
    > Skype for Business と Outlook を初めて起動した後、MAPI の状態が **[OK]** として表示されるまでに数分かかることがあります。
  
- セキュリティグループの作成とそのセキュリティグループの委任権限の追加はサポートされていません。
    
- MAPI は使用できません。 [Skype For business 2016 クライアントでの "MAPI は利用できません" エラーを](https://support.microsoft.com/en-us/help/3147130)参照してください。
    
- Skype for Business クライアントから Exchange Online メールボックスにアクセスすることはできません。 この問題が発生した場合は、 [Outlook 接続テスト](https://testconnectivity.microsoft.com/)を実行して、合格していることを確認してください。
    
## <a name="related-topics"></a>関連トピック
[Skype for Business Online のセットアップ](set-up-skype-for-business-online.md)

[Skype for Business ユーザーが Skype の連絡先を追加できるようにする](let-skype-for-business-users-add-skype-contacts.md)

  
 
