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
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Setup
description: この資料を設定し、オンライン ビジネスの委任のため Skype をトラブルシューティングする方法について説明します。 この記事では、設定の推奨事項、ベスト ・ プラクティス、およびトラブルシューティング手順を実行するためのガイダンスを提供します。
ms.openlocfilehash: 450aee07691a007b976aafffc05d34c3e7ef85f2
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30887837"
---
# <a name="set-up-and-troubleshoot-skype-for-business-online-delegation"></a>Skype for Business Online の代理のセットアップとトラブルシューティング

この資料を設定し、オンライン ビジネスの委任のため Skype をトラブルシューティングする方法について説明します。 この記事では、設定の推奨事項、ベスト ・ プラクティス、およびトラブルシューティング手順を実行するためのガイダンスを提供します。
  
## <a name="guidelines-and-requirements"></a>ガイドラインと要件

### <a name="guidelines-for-delegation"></a>委任のためのガイドライン

設定して、委任が正しく機能するを取得するには、これらのガイドラインに従う場合に依存します。
  
- 必要がありますを使用するビジネス 2015年最新の更新プログラムの完全なクライアントの Skype または、Skype ビジネス 2016年完全なクライアントの。
    
- 最新の更新プログラムで Outlook 2013 クライアントまたは Outlook 2016 クライアントを使っている必要があります。
    
- 委任者と代理人のコンピューターがある 1 つの Outlook メール プロファイルがプライマリまたは既定のプロファイルを確認します。 そのメール プロファイルは、1 つだけアカウントを含める必要があります。
    
- 代理人と代理人のための Skype では、オンライン ユーザーをする必要があります。 また、両方オンラインにするか両方に設置する必要があります、各アカウントの Exchange Server メールボックスです。
    
- 委任者と代理人の両方に同じメジャー バージョンの Outlook を使用する必要があります。
    
- **True**クライアント ポリシーでは、 **EnableExchangeDelegateSync**属性の値を設定してください。 この設定を確認するには、ビジネス オンラインの PowerShell モジュールの Skype で**Get CSClientPolicy**コマンドレットを実行します。
    
- 委任者と代理人署名が必要 Skype をビジネスおよび Outlook を同時に別のワークステーションで。
    
- 共有メールボックスは、オンライン ビジネスの委任のための Skype のサポートされていません。 共有メールボックスは、 **sendonbehalf**のアクセス制御リスト (ACL) を持っていないためにです。
    
### <a name="skype-for-business-client-version-support"></a>ビジネス クライアントのバージョンをサポートするための Skype

||**Outlook 2013**|**Outlook 2016**|
|:-----|:-----|:-----|
|**Lync と Skype クライアントの基本的なビジネスの**| サポートされていません |サポートされていません
|**Skype for Business 2015**|サポート対象| サポート対象|
|**ビジネス 2016年の Skype**|サポート対象| サポート対象|

   
### <a name="licensing-requirements"></a>ライセンスの要件

**E3 のエンタープライズ ライセンスのシナリオ**

|**ライセンス**|**クライアント**|**メモ**|
|:-----|:-----|:-----|
|エンタープライズ E3  <br/> |Outlook 2013 または 2016 の Outlook で使用される Lync 2013 (Skype ビジネス 2015年の)  <br/> Outlook 2013 または 2016 の Outlook で使用されるビジネス 2016年の Skype  <br/> |ビジネスの基本的なクライアントの Skype では、委任をサポートしていません。  <br/> Mac クライアントは、呼び出しがない会議に委任できます。  <br/> |
|Office 365 の電話システムと Office 365 xCalling プランとエンタープライズ E3  <br/> |Outlook 2013 または 2016 の Outlook で使用される Lync 2013 (Skype ビジネス 2015年の)  <br/> Outlook 2013 または 2016 の Outlook で使用されるビジネス 2016年の Skype  <br/> Lync for Mac 2011  <br/> |ビジネスの基本的なクライアントの Skype では、委任をサポートしていません。  <br/> Mac クライアントは、呼び出しがない会議に委任できます。  <br/> |
   
**E5 のエンタープライズ ライセンスのシナリオ**

|**ライセンス**|**クライアント**|**メモ**|
|:-----|:-----|:-----|
|エンタープライズ E5  <br/> |Lync 2013 (ビジネス 2015年の Skype) 2013 の Outlook または Outlook 2016 を使用します。  <br/> Outlook 2013 または 2016 の Outlook で使用されるビジネス 2016年の Skype  <br/> |ビジネスの基本的なクライアントの Skype では、委任をサポートしていません。  <br/> Mac クライアントは、呼び出しがない会議に委任できます。  <br/> |
|エンタープライズ E5 と Office 365 の通話プラン  <br/> |Mac 2016 のための Skype  <br/> Outlook 2013 または 2016 の Outlook で使用される Lync 2013 (Skype ビジネス 2015年の)  <br/> Outlook 2013 または 2016 の Outlook で使用されるビジネス 2016年の Skype  <br/> Lync for Mac 2011  <br/> |ビジネスの基本的なクライアントの Skype では、委任をサポートしていません。  <br/> Mac クライアントは、呼び出しがない会議に委任できます。  <br/> |
   
## <a name="set-up-and-verify-delegation"></a>設定し、委任の確認

オンライン ビジネスの委任のために、Skype を設定するには、次の手順を実行します。
  
### <a name="for-windows-clients"></a>Windows クライアントの

 **着信の転送] タブ**
  
1. **ツール**を選択して > **オプション** > **の設定の転送を呼び出します**。
    
2. **自分の代理人のメンバーを編集**] を選択します。
    
3. **追加**] を選択、追加する代理人を選択し、 **[ok]** を選択します。
    
 **呼び出しの転送タブが表示されません。**
  
1. Outlook では、**ファイル**を選択します > **アカウントの設定** > **代理人アクセス** > **追加**します。
    
2. 見つけるし、代理人になる人の名前を追加します。
    
3. [**予定表**] メニューを選択し、選択**エディター (読み取り、作成、および変更できますアイテム)**。
    
### <a name="for-mac-clients---lync"></a>Mac クライアントの Lync の

 **着信の転送] タブ**
  
- クライアントは、[**自分の代理人のメンバーを編集**] リンクを持つ**呼び出しの転送**] タブがありません、代理人が Mac コンピューター上にある場合は、代理人にサインインしなければなりません、Windows ベースのコンピューターで委任を設定するのには。 Mac クライアントは、MAPI 接続をすることはできませんし、これは、Outlook からの業務の委任のため Skype を確立する必要があるためにです。
    
### <a name="verify-success"></a>成功を確認します。

**_Lt _ Name> の代理人として追加されている場合**、代理人は見る必要があります、セットアップが成功した場合は、メッセージ、および**呼び出しの管理の人に**グループを作成します。 代理人は**代理人**のグループが作成されるはずです。
  
> [!NOTE]
> 委任アクセス許可は、通常のセットアップ プロセスの 30 分以内で表示されます。 ただし、最大 24 時間かかることができます。 
  
## <a name="troubleshooting"></a>トラブルシューティング

### <a name="common-issues"></a>一般的な問題

- > **問題 1**代理エントリに引き続き表示されます**呼び出しの管理の人が私**のグループ、代理人が Outlook クライアントからデリゲートを削除後します。
    
  - > **解決方法 1**ビジネス クライアント用の Skype で [**代理人**] で、代理人を右クリックし [**グループから削除**します。
    
- > **問題 2**Outlook クライアントを代理人アクセスが許可されると後は、代理人の確認のメッセージも、**呼び出しの管理の人が私**のグループが表示されます。
    
  - > **解決方法 2**Outlook クライアントからの委任を削除して、レプリケーションは、約 15 分間待ちます、代理人を追加し直す。
    
### <a name="other-common-issues"></a>その他の一般的な問題

- 25 委任者と代理人の 25 のしきい値を超えた場合、委任が動作しません。
    
- ビジネスの基本的なクライアントの Skype はサポートされていません。
    
    > [!NOTE]
    > ビジネスの基本的なクライアントの Skype をインストールするは削除して、委任を解除します。 
  
- **MAPI のステータス**値には、 **[ok]** がない場合は、 **SIP**と**SMTP**の値と一致していることを確認します。
    
    > [!NOTE]
    > ビジネスおよび Outlook の Skype を初めて起動した後、 **[ok]** として表示するのには MAPI の状態までに数分かかることができます。
  
- セキュリティ グループを作成し、そのセキュリティ グループのアクセス許可を委任を追加することがサポートされていません。
    
- MAPI が使用可能ではありません。 [Skype ビジネス 2016年のクライアントで"MAPI を使用できません"エラー](https://support.microsoft.com/en-us/help/3147130)を参照してください。
    
- Exchange Online のメールボックスは、ビジネス クライアント用の Skype を介してアクセスできません。 この問題が発生した場合は、 [Outlook の [接続のテスト](https://testconnectivity.microsoft.com/)に合格したことを確認するを実行します。
    
## <a name="related-topics"></a>関連項目
[Skype for Business Online のセットアップ](set-up-skype-for-business-online.md)

[Skype for Business ユーザーが Skype の連絡先を追加できるようにする](let-skype-for-business-users-add-skype-contacts.md)

  
 
