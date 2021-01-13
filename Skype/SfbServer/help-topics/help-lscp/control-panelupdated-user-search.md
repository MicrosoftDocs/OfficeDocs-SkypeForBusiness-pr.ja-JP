---
title: コントロール パネル - 更新されたユーザー検索
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 5/21/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.UserMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 50feb75f-92a1-4916-b92e-c039e1290c52
description: 検索クエリの結果を使用して、Skype for Business Server のユーザーを構成できます。 ユーザーは、表示名、名、姓、セキュリティ アカウント マネージャー (SAM) のアカウント名、SIP アドレス、または回線 URI (Uniform Resource Identifier) で検索できます。 Lync Server コントロール パネルまたは Active Directory ユーザーとコンピューター スナップインを使用して、ユーザーを検索することもできます。
ms.openlocfilehash: 699f0a4eeb07eb1ac056cdf4777853b163fdb1c0
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49800367"
---
# <a name="control-panel---updated-user-search"></a>コントロール パネル - 更新: ユーザー検索

検索クエリの結果を使用して、Skype for Business Server のユーザーを構成できます。 ユーザーは、表示名、名、姓、セキュリティ アカウント マネージャー (SAM) のアカウント名、SIP アドレス、または回線 URI (Uniform Resource Identifier) で検索できます。 Lync Server コントロール パネルまたは Active Directory ユーザーとコンピューター スナップインを使用して、ユーザーを検索することもできます。

## <a name="tasks-you-can-perform"></a>実行できるタスク

[ユーザー検索コントロール パネル] ページでは、 **次のタスク** を実行できます。

- [Lync Server 2010 ユーザーの検索](https://technet.microsoft.com/library/3b9f6f55-d7a9-46ae-8e10-f221ba0d3bb5.aspx)

- [Lync Server 2010 のユーザーを有効または無効にする](https://technet.microsoft.com/library/12497d00-f665-4a97-be68-854c5a8be4fc.aspx)

- [ユーザーの移動](move-user.md)

- [すべてのユーザーの移動](move-all-users.md)

- [ユーザーにポリシーを割り当てる](https://technet.microsoft.com/library/a4ed0120-d9e5-4eb2-acfd-8de2cb503652.aspx)

- [Skype for Business Server 2015 でエンタープライズ VoIPのユーザーを有効にする](../../deploy/deploy-enterprise-voice/enable-users-for-enterprise-voice.md)

- [ユーザーのフェデレーション、リモート ユーザー アクセス、およびパブリック IM 接続の構成](https://technet.microsoft.com/library/736fcaad-9f95-4896-b767-e199d86a00a4.aspx)

- [ユーザーのテレフォニーの構成](https://technet.microsoft.com/library/4546432e-c839-4517-a2c5-bc0d4d8c6a03.aspx)

Skype for Business Server コントロール パネルを使用して実行できるさまざまな手順の詳細については [、「Skype for Business Server 2015](../../manage/manage.md)の管理」を参照してください。

## <a name="ui-reference"></a>UI リファレンス

以下のリストでは、[**ユーザー検索**] ページ上のメニュー、コマンド、フィールド、およびプロパティーについて説明しています。

### <a name="user-search"></a>ユーザー検索

- **検索** ユーザー アカウントの表示名、名、氏名、SAM アカウント名、SIP アドレス、または回線 URI の最初の部分でユーザーを検索します。

- **LDAP 検索** LDAP 式を入力してユーザーを検索します。

- **[ユーザーの検索] ボックス** 検索するユーザー データまたは LDAP 式を入力します。

- **検索** クリックすると、[検索ユーザーと検索] ボックスに入力した検索値に一致する **ユーザーが** 表示されます。

- **クエリを開く** 保存した検索クエリをクリックして開きます。

- **クエリを保存する** クリックして検索クエリを保存します。

- **+ フィルターの追加** クリックして、追加の検索条件を追加します。

- **検索フィルター フィールド** 検索結果をフィルター処理するフィールドを選択し、クエリの演算子を選択して、検索する文字列を入力します。

- **表示する最大ユーザー数** 表示する検索結果の数を入力するか、上下の矢印を使用して数を指定します。

必要に応じて、説明テキストを追加します。

### <a name="search-results-menus"></a>検索結果メニュー

- **ユーザーを有効にする** Click to open the [Users: New Lync Server User](users-new-lync-server-user.md) dialog, where you can add a new user to Skype for Business Server.

    新規連絡先を追加するには、下矢印をクリックして [**連絡先を有効にする**] を選択し、[[Users: New Contact Objects](users-new-contact-objects.md)] ダイアログを開きます。

- **編集**[**編集]** をクリックし、[詳細の表示] をクリックして選択したユーザーの詳細を表示するか、[すべての検索結果を選択] をクリックして結果テーブルに表示されるユーザーを選択します。

- **アクション** [ **アクション]** をクリックし、検索結果で選択したユーザーに対して実行するアクションを選択します。 次のアクションを使用できます。

  - **Lync Server の再有効化** 一時的に無効にした後、選択したユーザー アカウントを有効にします。

  - **Lync Server の一時的な無効化** ユーザー アカウントを削除せずに、ユーザー アカウントを再び有効にするまで、Skype for Business Server でユーザー アカウントを無効にします。

  - **ポリシーの割り当て** [ユーザー [: ポリシーの割り](users-assign-policies.md) 当て] ダイアログを開き、ユーザーに割り当てられているポリシーを構成できます。

  - **PIN の状態を表示する** [ユーザー [: PIN の状態の](users-view-pin-status.md) 表示] ダイアログを開きます。このダイアログ ボックスには、選択したユーザーの PIN データが表示されます。

  - **PIN の設定** [PIN [の設定]](set-pin.md) ダイアログを開き、選択したユーザーの PIN を設定できます。

  - **PIN のロック** ユーザーの PIN をロックします。

  - **PIN のロック解除** ユーザーの PIN のロックを削除します。

  - **Lync Server からの削除** Skype for Business Server からユーザー アカウントを削除します。 ユーザーは Active Directory から削除されません。

  - **ユーザー証明書を削除する** ユーザーに付与されている証明書を削除します。

  - **選択したユーザーをプールに移動する** [ユーザー [の移動]](move-user.md) ダイアログを開き、選択したユーザーの移動先のプールを選択できます。

  - **すべてのユーザーをプールに移動する** [ユーザー [の移動]](move-user.md) ダイアログを開き、選択したユーザーの移動先のプールを選択できます。


