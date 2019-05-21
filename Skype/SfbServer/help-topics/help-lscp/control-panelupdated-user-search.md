---
title: コントロールパネル-ユーザー検索の更新
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 5/21/2015
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.UserMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 50feb75f-92a1-4916-b92e-c039e1290c52
description: 検索クエリの結果を使用して、Skype for Business Server のユーザーを構成することができます。 ユーザーは、表示名、名、姓、セキュリティ アカウント マネージャー (SAM) のアカウント名、SIP アドレス、または回線 URI (Uniform Resource Identifier) で検索できます。 ユーザーの検索には、Lync Server コントロール パネルまたは Active Directory ユーザーおよびコンピューター スナップインを使用できます。
ms.openlocfilehash: 7b6b72275ffd5dfe8c03b41d4da2ca8ee6f40a3a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34286003"
---
# <a name="control-panel---updated-user-search"></a>コントロール パネル - 更新: ユーザー検索

検索クエリの結果を使用して、Skype for Business Server のユーザーを構成することができます。 ユーザーは、表示名、名、姓、セキュリティ アカウント マネージャー (SAM) のアカウント名、SIP アドレス、または回線 URI (Uniform Resource Identifier) で検索できます。 ユーザーの検索には、Lync Server コントロール パネルまたは Active Directory ユーザーおよびコンピューター スナップインを使用できます。

## <a name="tasks-you-can-perform"></a>実行できるタスク

コントロール パネルの [**ユーザー検索**] ページでは以下のタスクを実行できます。

- [Search for Lync Server 2010 Users](https://technet.microsoft.com/library/3b9f6f55-d7a9-46ae-8e10-f221ba0d3bb5.aspx)

- [Enable or Disable Users for Lync Server 2010](https://technet.microsoft.com/library/12497d00-f665-4a97-be68-854c5a8be4fc.aspx)

- [ユーザーの移動](move-user.md)

- [すべてのユーザーの移動](move-all-users.md)

- [Assign Policies to Users](https://technet.microsoft.com/library/a4ed0120-d9e5-4eb2-acfd-8de2cb503652.aspx)

- [Enable users for Enterprise Voice in Skype for Business Server 2015](../../deploy/deploy-enterprise-voice/enable-users-for-enterprise-voice.md)

- [Configure Federation, Remote User Access, and Public IM Connectivity for Users](https://technet.microsoft.com/library/736fcaad-9f95-4896-b767-e199d86a00a4.aspx)

- [Configure Telephony for Users](https://technet.microsoft.com/library/4546432e-c839-4517-a2c5-bc0d4d8c6a03.aspx)

Skype for Business Server コントロールパネルを使用して実行できるさまざまな手順の詳細については、「Skype for business [server 2015 を管理](../../manage/manage.md)する」を参照してください。

## <a name="ui-reference"></a>UI リファレンス

以下のリストでは、[**ユーザー検索**] ページ上のメニュー、コマンド、フィールド、およびプロパティについて説明しています。

### <a name="user-search"></a>ユーザー検索

- **検索**ユーザーアカウントの表示名、姓、名、SAM アカウント名、SIP アドレス、またはライン URI の最初の部分でユーザーを検索します。

- **LDAP 検索**LDAP 式を入力してユーザーを検索します。

- **[ユーザーの検索] ボックス**抽出するユーザーデータまたは LDAP 条件式を入力します。

- **検索**[**ユーザーとユーザーの検索**] ボックスに入力した検索値と一致するユーザーをクリックして表示します。

- **クエリを開く**保存されている検索クエリをクリックして開きます。

- **クエリの保存**検索クエリを保存するには、をクリックします。

- **+ フィルターの追加**追加の検索条件を追加するには、をクリックします。

- **検索フィルターフィールド**検索結果をフィルター処理するフィールドを選び、クエリの演算子を選んで、検索する文字列を入力します。

- **表示するユーザーの最大数**表示する検索結果の数を入力するか、上下の矢印を使用して番号を指定します。

必要に応じて、説明テキストを追加します。

### <a name="search-results-menus"></a>検索結果メニュー

- **ユーザーを有効にする**クリックすると、[[ユーザー: 新しい Lync Server ユーザー](users-new-lync-server-user.md) ] ダイアログが開き、Skype For business server に新規ユーザーを追加できます。

    新規連絡先を追加するには、下矢印をクリックして [**連絡先を有効にする**] を選択し、[[Users: New Contact Objects](users-new-contact-objects.md)] ダイアログを開きます。

- **編集**[**編集**] をクリックし、[**詳細の表示**] をクリックして選択したユーザーの詳細を表示するか、[**すべての検索結果の選択**] をクリックして、結果テーブルに表示されているすべてのユーザーを選択します。

- **操作**[**アクション**] をクリックし、検索結果で選択したユーザーに対して実行する操作を選びます。 次の操作を実行できます。

  - **Lync Server の再有効化**選択したユーザーアカウントが一時的に無効にされた後で有効にします。

  - **Lync Server を一時的に無効にする**ユーザーアカウントを削除せずに、Skype for Business Server のユーザーアカウントを無効にします。

  - **ポリシーを割り当てる**[[ユーザー: ポリシーの割り当て](users-assign-policies.md)] ダイアログが開き、ユーザーに割り当てられているポリシーを構成できます。

  - **PIN の状態を表示**する[[ユーザー: pin の状態の表示](users-view-pin-status.md)] ダイアログを開きます。選択したユーザーの pin データが表示されます。

  - **PIN を設定**する[ [Pin の設定](set-pin.md)] ダイアログを開きます。このダイアログボックスでは、選択したユーザーの pin を設定できます。

  - **ロックピン**ユーザーの PIN をロックします。

  - **PIN のロックを解除**するユーザーの PIN のロックを解除します。

  - **Lync Server から削除**するSkype for Business Server からユーザーアカウントを削除します。 ユーザーは Active Directory から削除されません。

  - **ユーザー証明書を削除**するユーザーに付与されているすべての証明書を削除します。

  - **選択したユーザーをプールに移動する**[[ユーザーの移動](move-user.md)] ダイアログが開きます。このダイアログボックスでは、選択したユーザーを移動するプールを選択できます。

  - **すべてのユーザーをプールに移動する**[[ユーザーの移動](move-user.md)] ダイアログが開きます。このダイアログボックスでは、選択したすべてのユーザーを移動するプールを選択できます。


