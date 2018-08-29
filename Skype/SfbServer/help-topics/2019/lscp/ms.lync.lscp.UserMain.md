---
title: コントロール パネルの更新されたユーザーの検索
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.UserMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 50feb75f-92a1-4916-b92e-c039e1290c52
ROBOTS: NOINDEX, NOFOLLOW
description: Skype のビジネス サーバーのユーザーを構成するのには、検索クエリの結果を使用できます。 ユーザーは、表示名、名、姓、セキュリティ アカウント マネージャー (SAM) のアカウント名、SIP アドレス、または回線 URI (Uniform Resource Identifier) で検索できます。 ユーザーの検索には、Lync Server コントロール パネルまたは Active Directory ユーザーおよびコンピューター スナップインを使用できます。
ms.openlocfilehash: 79a12b5b420b355376e544d8a51db8e24142bea0
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/28/2018
ms.locfileid: "23245685"
---
# <a name="control-panel---updated-user-search"></a>コントロール パネル - 更新: ユーザー検索

Skype のビジネス サーバーのユーザーを構成するのには、検索クエリの結果を使用できます。 ユーザーは、表示名、名、姓、セキュリティ アカウント マネージャー (SAM) のアカウント名、SIP アドレス、または回線 URI (Uniform Resource Identifier) で検索できます。 ユーザーの検索には、Lync Server コントロール パネルまたは Active Directory ユーザーおよびコンピューター スナップインを使用できます。

## <a name="tasks-you-can-perform"></a>実行できるタスク

コントロール パネルの [**ユーザー検索**] ページでは以下のタスクを実行できます。

- [ユーザーを検索します。](https://technet.microsoft.com/library/3b9f6f55-d7a9-46ae-8e10-f221ba0d3bb5.aspx)

- [有効または無効にするユーザー](https://technet.microsoft.com/library/12497d00-f665-4a97-be68-854c5a8be4fc.aspx)

- [ユーザーの移動](ms.lync.lscp.UserMove.md)

- [すべてのユーザーの移動](ms.lync.lscp.UserMoveAll.md)

- [ユーザーにポリシーを割り当てる](https://technet.microsoft.com/library/a4ed0120-d9e5-4eb2-acfd-8de2cb503652.aspx)

- [ビジネス サーバーの Skype でエンタープライズ VoIP のユーザーを有効にします。](../../../deploy/deploy-enterprise-voice/enable-users-for-enterprise-voice.md)

- [ユーザーのフェデレーション、リモート ユーザー アクセス、およびパブリック IM 接続を構成します。](https://technet.microsoft.com/library/736fcaad-9f95-4896-b767-e199d86a00a4.aspx)

- [ユーザーのテレフォニーを構成します。](https://technet.microsoft.com/library/4546432e-c839-4517-a2c5-bc0d4d8c6a03.aspx)



## <a name="ui-reference"></a>UI リファレンス

以下のリストでは、[**ユーザー検索**] ページ上のメニュー、コマンド、フィールド、およびプロパティについて説明しています。

### <a name="user-search"></a>ユーザー検索

- **検索**表示名、名、姓、名、SAM アカウント名、SIP アドレスの最初の部分でユーザーを検索するか、ユーザー アカウントの URI の行。

- **LDAP 検索**LDAP 式を入力してユーザーを検索します。

- **検索ボックス**ユーザー データを検索する LDAP 表現を入力します。

- **検索****ユーザーを検索**し、ボックスに入力した検索値に一致するユーザーを表示する] をクリックします。

- **クエリを開く**保存済み検索クエリを開く] をクリックします。

- **クエリを保存します。** 検索クエリを保存する] をクリックします。

- **+ フィルターの追加**追加の検索条件を追加する] をクリックします。

- **検索フィルターのフィールド**検索結果をフィルター処理、クエリでは、オペレーターを選択し、検索する文字列を入力するフィールドを選択します。

- **最大ユーザー数を表示するには**表示、またはを使用して上下の矢印の数を指定する検索結果の数を入力します。

必要に応じて、説明テキストを追加します。

### <a name="search-results-menus"></a>検索結果メニュー

- **ユーザーを有効にします。** 開く] をクリックして、[ユーザー: Lync Server のユーザーが新しい](ms.lync.lscp.UserNew.md)ダイアログ ボックスで、ビジネスのサーバーの Skype に新しいユーザーを追加する場所です。

    新しい連絡先を追加する、下向きの矢印をクリックし、**連絡先を有効にする**を開くには、[ユーザー: 新しい連絡先オブジェクト](ms.lync.lscp.UserNewContact.md)ダイアログです。

- **編集**[**編集**] をクリックし、選択したユーザーの詳細を表示または**検索結果をすべて選択**結果テーブルに表示されるすべてのユーザーを選択する] をクリックして**詳細を表示する**をクリックします。

- **アクション****アクション**をクリックし、検索結果で選択したユーザーは、実行するアクションを選択します。 次の操作を紹介します。

  - **Lync Server に再度有効にします。** 一時的に無効には、選択したユーザーのアカウントを有効にします。

  - **Lync Server を一時的に無効にします。** 再度有効にするまで、ユーザー アカウントを削除することがなく、ビジネス サーバーの Skype のユーザー アカウントを無効にします。

  - **ポリシーを割り当てる**開き、[ユーザー: ポリシーの割り当て](ms.lync.lscp.UserAssignPolicy.md)ダイアログ ボックスで、ユーザーに割り当てられているポリシーを構成することができます。

  - **表示ピンの状態**開き、[ユーザー: 暗証番号 (pin) の状態を表示する](ms.lync.lscp.UserViewPin.md)ダイアログ ボックスで、選択したユーザーの暗証番号 (pin) のデータが表示されます。

  - **暗証番号 (pin) を設定します。** 選択したユーザーの PIN を設定できます、[暗証番号 (pin) の設定](ms.lync.lscp.UserSetPin.md)」ダイアログが開きます。

  - **ロック暗証番号 (pin)** ユーザーの暗証番号 (pin) をロックします。

  - **暗証番号 (pin) のロックを解除します。** ユーザーの暗証番号 (pin) のロックを削除します。

  - **Lync Server から削除します。** Skype からビジネスのサーバーのユーザー アカウントを削除します。 ユーザーが Active Directory から削除されません。

  - **ユーザー証明書を削除**ユーザーに与えられているすべての証明書を削除します。

  - **プールを選択したユーザーの移動**選択したユーザーを移動するプールを選択することができます、[ユーザーの移動](ms.lync.lscp.UserMove.md)」ダイアログが開きます。

  - **プールへのすべてのユーザーを移動します。** 選択したすべてのユーザーを移動するプールを選択することができます、[ユーザーの移動](ms.lync.lscp.UserMove.md)」ダイアログが開きます。


