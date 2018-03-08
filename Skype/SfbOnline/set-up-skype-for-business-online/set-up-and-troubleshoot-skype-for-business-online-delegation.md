---
title: "セットアップし、トラブルシューティング Skype for Business Online の委任"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 01/22/2018
ms.topic: article
ms.assetid: e676b911-5f82-41d8-b4ce-3d0d45c3cd04
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Setup
description: "この記事では、セットアップし、トラブルシューティング Skype for Business Online の委任する方法について説明します。この記事では、設定の推奨事項、ベスト プラクティス、およびトラブルシューティング手順を実行するためのガイダンスを提供します。"
ms.openlocfilehash: b69f6712f78906bc955d3ce014fe8ccd6ab252c1
ms.sourcegitcommit: 2d84f687ccc44220d5ec9d8b429dfae65cced5a7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/01/2018
---
# <a name="set-up-and-troubleshoot-skype-for-business-online-delegation"></a>セットアップし、トラブルシューティング Skype for Business Online の委任

この記事では、セットアップし、トラブルシューティング Skype for Business Online の委任する方法について説明します。この記事では、設定の推奨事項、ベスト プラクティス、およびトラブルシューティング手順を実行するためのガイダンスを提供します。
  
## <a name="guidelines-and-requirements"></a>ガイドラインと要件

### <a name="guidelines-for-delegation"></a>委任するためのガイドライン

正常に動作する代理人の作業をセットアップするには、次のガイドラインをフォローするに依存します。
  
- 使用が必要 Skype for Business 2015 フル機能の最新の更新プログラムでクライアントまたは Skype for Business 2016 の完全なクライアントです。
    
- 最新の更新プログラムで Outlook 2013 クライアントまたは Outlook 2016 クライアントを使っている必要があります。
    
- 代理人のコンピューターと代理人がプライマリは、1 つの Outlook メール プロファイルまたは既定のプロファイルがあることを確認します。メール プロファイルにはする必要がありますが含まれているアカウント 1 つだけにはです。
    
- Skype for Business の代理人と代理人は、オンラインのユーザーになります。また、必要があります両方オンラインにするか、両方の内部設置型の各アカウントの Exchange Server メールボックスします。
    
- 代理人と代理人の両方に同じメジャー バージョンの Outlook を使用する必要があります。
    
- **条件を満たす**クライアント ポリシーのする**EnableExchangeDelegateSync**属性値に設定する必要があります。Skype for Business Online PowerShell モジュール**Get CSClientPolicy**コマンドレットを実行してこの設定を確認することができます。
    
- 代理人と代理人の両方必要がありますへのサインインが Skype for Business と Outlook 同時に別のワークステーションにします。
    
- 共有メールボックスは Skype for Business Online の委任のサポートされていません。共有メールボックスは**sendonbehalf**アクセス制御リスト (ACL) があるないためにです。
    
### <a name="skype-for-business-client-version-support"></a>Skype for Business クライアント バージョンのサポート

||**Outlook 2013**|**Outlook 2016**|
|:-----|:-----|:-----|
|**Lync と Skype for Business の基本的なクライアント**| サポート対象外 |サポート対象外
|**Skype for Business 2015**|サポートされます| サポートされます|
|**Skype for Business 2016**|サポートされます| サポートされます|

   
### <a name="licensing-requirements"></a>ライセンス要件

**Enterprise E3 ライセンス シナリオ**

|**ライセンス**|**クライアント**|**ノート**|
|:-----|:-----|:-----|
|Enterprise E3  <br/> |Lync 2013 (Skype for Business 2015) Outlook 2013 または Outlook 2016 を使用  <br/> Skype for Business 2016 を Outlook 2013 または Outlook 2016 を使用  <br/> |Skype for Business の基本的なクライアントでは、委任をサポートしていません。  <br/> Mac クライアントでは、通話、会議ではなくを委任することができます。  <br/> |
|Office 365 の電話システムと Office 365 xCalling プランと Enterprise E3  <br/> |Lync 2013 (Skype for Business 2015) Outlook 2013 または Outlook 2016 を使用  <br/> Skype for Business 2016 を Outlook 2013 または Outlook 2016 を使用  <br/> Lync for Mac 2011  <br/> |Skype for Business の基本的なクライアントでは、委任をサポートしていません。  <br/> Mac クライアントでは、通話、会議ではなくを委任することができます。  <br/> |
   
**エンタープライズ E5 ライセンス シナリオ**

|**ライセンス**|**クライアント**|**ノート**|
|:-----|:-----|:-----|
|エンタープライズ E5  <br/> |Lync 2013 (Skype for Business 2015) Outlook 2013 または Outlook 2016 を使用します。  <br/> Skype for Business 2016 を Outlook 2013 または Outlook 2016 を使用  <br/> |Skype for Business の基本的なクライアントでは、委任をサポートしていません。  <br/> Mac クライアントでは、通話、会議ではなくを委任することができます。  <br/> |
|エンタープライズ E5 と Office 365 の通話プラン  <br/> |Skype for Business for Mac 2016  <br/> Lync 2013 (Skype for Business 2015) Outlook 2013 または Outlook 2016 を使用  <br/> Skype for Business 2016 を Outlook 2013 または Outlook 2016 を使用  <br/> Lync for Mac 2011  <br/> |Skype for Business の基本的なクライアントでは、委任をサポートしていません。  <br/> Mac クライアントでは、通話、会議ではなくを委任することができます。  <br/> |
   
## <a name="set-up-and-verify-delegation"></a>セットアップして、呼び出しを確認します。

Skype for Business Online の委任をセットアップするには、これらの手順に従います。
  
### <a name="for-windows-clients"></a>Windows クライアント

 **着信の転送] タブ**
  
1. **ツール**を選択する > **オプション** > **着信の転送設定**します。
    
2. **代理人メンバーの編集**] を選びます。
    
3. **追加**] を選択、代理人を追加するを選択し、[ **ok]**をクリックします。
    
 **着信の転送タブが表示されません。**
  
1. Outlook では、**ファイル**の選択 > **アカウント設定** > **代理人アクセス** > **追加**します。
    
2. 見つけてを代理人を務める人の名前を追加します。
    
3. [**予定表**] メニューを選択し、選択**エディター (読み取り、作成、およびアイテムの変更)**します。
    
### <a name="for-mac-clients---lync"></a>Mac クライアント - Lync

 **着信の転送] タブ**
  
- クライアントは、[**代理人メンバーの編集**] リンクを含む**着信の転送**] タブがない場合は、代理人が Mac コンピューター上にある代理人必要がありますサインインを Windows ベースのコンピューターに委任を設定するためにします。Mac クライアントできない MAPI 接続を行い、これは、Outlook からビジネス委任の Skype を確立する必要があるためにです。
    
### <a name="verify-success"></a>成功を確認します。

代理人が**< 名 > の代理人として追加された場合**の表示セットアップが失敗した場合は、メッセージとも**通話を管理する連絡先が**グループを作成します。代理人の**代理人**グループを作成することが表示されます。
  
> [!NOTE]
> 委任の権限は、通常のセットアップ プロセスの 30 分以内で表示されます。ただし、完了するまで 24 時間かかることができます。 
  
## <a name="troubleshooting"></a>トラブルシューティング

### <a name="common-issues"></a>一般的な問題

- > **1 の問題**代理人のエントリは、代理人が Outlook クライアントから代理人を削除した後に**通話を管理する連絡先が**グループの表示を続けます。
    
  - > **解決方法 1**Skype for Business クライアントでは、**代理人**] で、代理人を右クリックし、[**グループから削除**] を選びます。
    
- > **2 の問題**Outlook クライアントを代理人アクセスを許可した後、確認メッセージも、**通話を管理する連絡先が**グループを代理人が表示されます。
    
  - > **解決方法 2**Outlook クライアントから委任を削除する、レプリケーションは、15 分待ってからもう一度、代理人を追加します。
    
### <a name="other-common-issues"></a>その他の一般的な問題

- 25 委任者と 25 の代理人のしきい値を超えた場合は、委任が機能しません。
    
- Skype for Business の基本的なクライアントはサポートされていません。
    
    > [!NOTE]
    > Skype for Business の基本的なクライアントをインストールしている場合、削除し、呼び出しを解除します。 
  
- **MAPI 状態**の値には、 **[ok]**がない場合は場合、は、 **SIP**および**SMTP**値と一致していることを確認します。
    
    > [!NOTE]
    > MAPI 状態 Business と Outlook の Skype を初めて起動した後は、 **[ok]**として表示するのには数分かかることができます。
  
- セキュリティ グループを作成して、セキュリティ グループの代理人のアクセス許可の追加はサポートされていません。
    
- MAPI では使用できません。[Skype for Business 2016 クライアントでの"MAPI は利用できません"エラー](https://support.microsoft.com/en-us/help/3147130)を参照してください。
    
- Exchange Online メールボックスに Skype for Business クライアントからアクセスできません。この問題が発生した場合は、要件を満たす必要かどうかを確認する[Outlook 接続のテスト](https://testconnectivity.microsoft.com/)を実行します。
    
## <a name="related-topics"></a>関連トピック
[Skype for Business Online をセットアップします。](set-up-skype-for-business-online.md)

[ビジネス ユーザー向けの Skype Skype の連絡先を追加できるようにします。](let-skype-for-business-users-add-skype-contacts.md)
