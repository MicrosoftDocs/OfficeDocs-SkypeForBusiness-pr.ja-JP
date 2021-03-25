---
title: コントロール パネル - 更新されたユーザー検索
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.UserMain
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 50feb75f-92a1-4916-b92e-c039e1290c52
ROBOTS: NOINDEX, NOFOLLOW
description: 検索クエリの結果を使用して、Skype for Business Server のユーザーを構成できます。 ユーザーは、表示名、名、姓、セキュリティ アカウント マネージャー (SAM) のアカウント名、SIP アドレス、または回線 URI (Uniform Resource Identifier) で検索できます。 Lync Server コントロール パネルまたは Active Directory ユーザーとコンピューター スナップインを使用してユーザーを検索することもできます。
ms.openlocfilehash: ff98ed04ce4d411c118e9b0b497a2118ba38e17e
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120096"
---
# <a name="control-panel---updated-user-search"></a>コントロール パネル - 更新: ユーザー検索

検索クエリの結果を使用して、Skype for Business Server のユーザーを構成できます。 ユーザーは、表示名、名、姓、セキュリティ アカウント マネージャー (SAM) のアカウント名、SIP アドレス、または回線 URI (Uniform Resource Identifier) で検索できます。 Lync Server コントロール パネルまたは Active Directory ユーザーとコンピューター スナップインを使用してユーザーを検索することもできます。

## <a name="tasks-you-can-perform"></a>実行できるタスク

[ユーザー検索] コントロール パネル ページでは、 **次のタスクを** 実行できます。

- [ユーザーの検索](/previous-versions/office/lync-server-2013/lync-server-2013-search-for-lync-server-users)

- [ユーザーを有効または無効にする](/previous-versions/office/lync-server-2013/lync-server-2013-disable-or-re-enable-user-account-for-lync-server)

- [ユーザーの移動](ms.lync.lscp.UserMove.md)

- [すべてのユーザーの移動](ms.lync.lscp.UserMoveAll.md)

- [ユーザーにポリシーを割り当てる](/previous-versions/office/lync-server-2013/lync-server-2013-assigning-per-user-policies)

- [Skype for Business Server でエンタープライズ VoIPユーザーを有効にする](../../../deploy/deploy-enterprise-voice/enable-users-for-enterprise-voice.md)

- [ユーザーのフェデレーション、リモート ユーザー アクセス、およびパブリック IM 接続を構成する](/previous-versions/office/lync-server-2013/lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user)

- [ユーザーのテレフォニーの構成](/previous-versions/office/lync-server-2013/lync-server-2013-configure-telephony-for-a-user)



## <a name="ui-reference"></a>UI リファレンス

以下のリストでは、[**ユーザー検索**] ページ上のメニュー、コマンド、フィールド、およびプロパティーについて説明しています。

### <a name="user-search"></a>ユーザー検索

- **検索** ユーザー アカウントの表示名、SAM アカウント名、SIP アドレス、または行 URI の最初の部分でユーザーを検索します。

- **LDAP 検索** LDAP 式を入力してユーザーを検索します。

- **[ユーザーの検索] ボックス** シークするユーザー データまたは LDAP 式を入力します。

- **検索** クリックすると、[検索ユーザーと検索] ボックスに入力した検索値に一致 **するユーザーが** 表示されます。

- **クエリを開く** クリックして、保存された検索クエリを開きます。

- **クエリの保存** クリックして検索クエリを保存します。

- **+ フィルターの追加** クリックして、追加の検索条件を追加します。

- **検索フィルター フィールド** 検索結果をフィルター処理するフィールドを選択し、クエリの演算子を選択し、検索する文字列を入力します。

- **表示する最大ユーザー数** 表示する検索結果の数を入力するか、上下の矢印を使用して数値を指定します。

必要に応じて、説明テキストを追加します。

### <a name="search-results-menus"></a>検索結果メニュー

- **ユーザーを有効にする** [ユーザー: 新しい [Lync Server ユーザー]](ms.lync.lscp.UserNew.md) ダイアログを開き、Skype for Business Server に新しいユーザーを追加できます。

    新規連絡先を追加するには、下矢印をクリックして [**連絡先を有効にする**] を選択し、[[Users: New Contact Objects](ms.lync.lscp.UserNewContact.md)] ダイアログを開きます。

- **編集**[**編集]** をクリックし、[詳細の表示] をクリックして選択したユーザーの詳細を表示するか、[すべての検索結果を選択] をクリックして、結果テーブルに表示されるすべてのユーザーを選択します。

- **アクション** [ **アクション]** をクリックし、検索結果で選択したユーザーに対して実行するアクションを選択します。 次のアクションを使用できます。

  - **Lync Server の再有効化** 一時的に無効にした後、選択したユーザー アカウントを有効にします。

  - **Lync Server の一時的な無効化** ユーザー アカウントを削除せずに、Skype for Business Server のユーザー アカウントを再び有効にするまで無効にします。

  - **ポリシーの割り当て** [ユーザー [: ポリシーの割り当て](ms.lync.lscp.UserAssignPolicy.md) ] ダイアログを開き、ユーザーに割り当てられたポリシーを構成できます。

  - **PIN の状態を表示する** [ユーザー [: PIN 状態の表示] ダイアログボックスが](ms.lync.lscp.UserViewPin.md) 開き、選択したユーザーの PIN データが表示されます。

  - **PIN の設定** [PIN の [設定]](ms.lync.lscp.UserSetPin.md) ダイアログを開き、選択したユーザーの PIN を設定できます。

  - **PIN のロック** ユーザーの PIN をロックします。

  - **PIN のロックを解除する** ユーザーの PIN のロックを削除します。

  - **Lync Server から削除する** Skype for Business Server からユーザー アカウントを削除します。 ユーザーは Active Directory から削除されません。

  - **ユーザー証明書の削除** ユーザーに付与された証明書をすべて削除します。

  - **選択したユーザーをプールに移動する** [ユーザー [の移動]](ms.lync.lscp.UserMove.md) ダイアログを開き、選択したユーザーを移動するプールを選択できます。

  - **すべてのユーザーをプールに移動する** [ユーザーの [移動]](ms.lync.lscp.UserMove.md) ダイアログを開き、プールを選択して選択したユーザー全員を移動できます。