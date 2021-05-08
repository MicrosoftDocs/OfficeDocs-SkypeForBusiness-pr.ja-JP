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
f1.keywords:
- NOCSH
ms.custom:
- Setup
description: この記事では、オンライン委任の設定とトラブルシューティングSkype for Business説明します。 この記事では、セットアップの推奨事項、ベスト プラクティス、およびトラブルシューティングの手順のガイダンスを提供します。
ms.openlocfilehash: e5c710849f5829a4a270dc327f71d98185e85c89
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/06/2021
ms.locfileid: "52239826"
---
# <a name="set-up-and-troubleshoot-skype-for-business-online-delegation"></a>Skype for Business Online の代理のセットアップとトラブルシューティング

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

この記事では、オンライン委任の設定とトラブルシューティングSkype for Business説明します。 この記事では、セットアップの推奨事項、ベスト プラクティス、およびトラブルシューティングの手順のガイダンスを提供します。
  
## <a name="guidelines-and-requirements"></a>ガイドラインと要件

### <a name="guidelines-for-delegation"></a>委任のガイドライン

委任を正しく機能するように設定および取得するには、次のガイドラインに従う必要があります。
  
- 最新の更新プログラムまたは Skype for Business 201 Skype for Business 6 フル クライアントで Skype for Business 2015 フル クライアントを使用している必要があります。
    
- 最新の更新プログラムまたはOutlook 2013 クライアントを使用Outlook 2016があります。
    
- 委任者と代理人のコンピューターに、プライマリ プロファイルOutlook既定のプロファイルであるメール プロファイルが 1 つ含め込み、 そのメール プロファイルには、1 つのアカウントのみを含む必要があります。
    
- Skype for Business代理人のユーザーはオンライン ユーザーである必要があります。 また、各Exchange Serverのメールボックスは、両方ともオンラインか、両方がオンプレミスである必要があります。
    
- 委任者と代理人の両方が、同じメジャー バージョンのアカウントを使用Outlook。
    
- クライアント **ポリシーで EnableExchangeDelegateSync** 属性値を **true** に設定する必要があります。 この設定を確認するには、オンライン PowerShell モジュールの Skype for Business **Get-CSClientPolicy** コマンドレットを実行します。
    
- 委任者と代理人の両方が、Skype for Businessにサインインし、Outlookワークステーションで同時にサインインする必要があります。
    
- 共有メールボックスは、オンライン委任のSkype for Businessサポートされていません。 これは、共有メールボックスに **sendonbehalf** アクセス制御リスト (ACL) が含まれるためです。
    
### <a name="skype-for-business-client-version-support"></a>Skype for Business クライアント バージョンのサポート

||**Outlook 2013**|**Outlook 2016**|
|:-----|:-----|:-----|
|**Lync/Skype for Business Basic クライアント**| 非サポート |非サポート
|**Skype for Business 2015**|サポート| サポート|
|**Skype for Business 2016**|サポート| サポート|

   
### <a name="licensing-requirements"></a>ライセンス要件

**EnterpriseE3 ライセンスシナリオ**

|**ライセンス**|**クライアント**|**メモ**|
|:-----|:-----|:-----|
|エンタープライズ E3  <br/> |2013 または Skype for Business で使用される Lync 2013 (Outlook 2015) Outlook 2016  <br/> Skype for Business 2013 または Outlook で使用される 2016 Outlook 2016  <br/> |Skype for BusinessBasic クライアントでは委任はサポートされていません。  <br/> Mac クライアントの場合、通話を委任できますが、会議は委任されません。  <br/> |
|EnterpriseE3 と Office 365 電話システム + Office 365 xCalling プラン  <br/> |2013 または Skype for Business で使用される Lync 2013 (Outlook 2015) Outlook 2016  <br/> Skype for Business 2013 または Outlook で使用される 2016 Outlook 2016  <br/> Lync for Mac 2011  <br/> |Skype for BusinessBasic クライアントでは委任はサポートされていません。  <br/> Mac クライアントの場合、通話を委任できますが、会議は委任されません。  <br/> |
   
**EnterpriseE5 ライセンスシナリオ**

|**ライセンス**|**クライアント**|**メモ**|
|:-----|:-----|:-----|
|EnterpriseE5  <br/> |Outlook 2013 または Outlook 2016 で使用される Lync 2013 (Skype for Business 2015)。  <br/> Skype for Business 2013 または Outlook で使用される 2016 Outlook 2016  <br/> |Skype for BusinessBasic クライアントでは委任はサポートされていません。  <br/> Mac クライアントの場合、通話を委任できますが、会議は委任されません。  <br/> |
|EnterpriseE5 + Office 365通話プラン  <br/> |Skype for Business for Mac 2016  <br/> 2013 または Skype for Business で使用される Lync 2013 (Outlook 2015) Outlook 2016  <br/> Skype for Business 2013 または Outlook で使用される 2016 Outlook 2016  <br/> Lync for Mac 2011  <br/> |Skype for BusinessBasic クライアントでは委任はサポートされていません。  <br/> Mac クライアントの場合、通話を委任できますが、会議は委任されません。  <br/> |
   
## <a name="set-up-and-verify-delegation"></a>委任を設定して確認する

オンライン委任をSkype for Businessするには、次の手順に従います。
  
### <a name="for-windows-clients"></a>Windows クライアントの場合

 **[通話の転送] タブ**
  
1. [ツール **] [**  >  **オプション]**  >  **[通話の転送] 設定。**
    
2. [代理人 **メンバーの編集] を選択します**。
    
3. [ **追加]** を選択し、追加する代理人を選択し **、[OK] を選択します**。
    
 **[通話の転送なし] タブ**
  
1. [Outlook で、[ファイル アカウント]**を**  >  **選択し、[代理人設定**  >  **追加] を**  >  **選択します**。
    
2. 代理人になるユーザーの名前を見つけて追加します。
    
3. [予定表] **メニューを** 選択し、[エディター] (アイテムの読み取り、作成、変更が **可能) を選択します**。
    
### <a name="for-mac-clients---lync"></a>Mac クライアントの場合 - Lync

 **[通話の転送] タブ**
  
- クライアントに [代理人メンバーの編集] リンクがある [通話の転送] タブが表示され、委任者が Mac コンピューター上にある場合、委任を設定するには、委任者が Windows ベースのコンピューターにサインインする必要があります。 これは、Mac クライアントが MAPI 接続を確立できないためであり、これは、ユーザーからの委任を確立Skype for Business要件Outlook。
    
### <a name="verify-success"></a>成功を確認する

セットアップが成功すると、代理人に **[< Name>** の代理人として追加されました] というメッセージが表示され、[通話を管理するユーザー  ] グループが作成されます。 委任者は、[代理人] グループ **が作成された** と表示されます。
  
> [!NOTE]
> 委任アクセス許可は、通常、セットアップ プロセスから 30 分以内に表示されます。 ただし、このプロセスが完了するには最大 24 時間かかる場合があります。 
  
## <a name="troubleshooting"></a>トラブルシューティング

### <a name="common-issues"></a>一般的な問題

- > **問題 1** 代理人エントリは、委任者が代理人をクライアントから削除した後も、[通話の管理を行うユーザー] グループOutlookされます。
    
  - > **解決策 1** 新しいSkype for Businessで、[代理人] グループの代理人を右クリックし、[グループから削除]**を選択します**。
    
- > **問題 2** Outlook クライアントを通じて代理人アクセスが許可された後、代理人の確認メッセージも [通話の管理するユーザー] グループも表示されません。
    
  - > **解決策 2** 委任をクライアントから削除Outlook約 15 分待ち、もう一度代理人を追加します。
    
### <a name="other-common-issues"></a>その他の一般的な問題

- 委任は、25 人の委任者と 25 人の代理人のしきい値を超えた場合は機能しません。
    
- Basic Skype for Businessはサポートされていません。
    
    > [!NOTE]
    > Skype for Business Basic クライアントをインストールすると、委任が削除され、破損します。 
  
- MAPI 状態 **の値が** OK ではない場合 **は、SIP** と SMTP の値が一致 **する必要** があります。 
    
    > [!NOTE]
    > MAPI の状態が[OK] と表示されるのは、最初に開始した後に **[OK]** Skype for Business数分Outlook。
  
- セキュリティ グループの作成と、そのセキュリティ グループの委任アクセス許可の追加はサポートされていません。
    
- MAPI は使用できません。 [2016 年 2016 年のクライアントで「MAPI を使用できない」Skype for Businessを参照してください](https://support.microsoft.com/help/3147130)。
    
- メールボックスExchange OnlineクライアントからアクセスSkype for Businessできません。 この場合は、接続テストOutlook[を実行して](https://testconnectivity.microsoft.com/)、接続テストに合格した必要があります。
    
## <a name="related-topics"></a>関連トピック
[Skype for Business Online をセットアップする](set-up-skype-for-business-online.md)

[Skype for Business ユーザーが Skype の連絡先を追加できるようにする](let-skype-for-business-users-add-skype-contacts.md)

  
 
