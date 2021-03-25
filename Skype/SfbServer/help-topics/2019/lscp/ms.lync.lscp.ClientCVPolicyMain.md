---
title: クライアント バージョン ポリシー
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.ClientCVPolicyMain
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 4f84bc0f-e1df-4acb-b8ef-57f165b0153b
ROBOTS: NOINDEX, NOFOLLOW
description: 現在の環境でサポートするクライアントのバージョンを指定できます。 バージョンが異なる 2 つのクライアントが対話する場合、機能によっては一方のクライアントでは使用できても、他方のクライアントでは使用できないことがあります。
ms.openlocfilehash: fd3abdae41b912e63391121c740912cde80e18c2
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120296"
---
# <a name="client-version-policy"></a>クライアント バージョン ポリシー

現在の環境でサポートするクライアントのバージョンを指定できます。 バージョンが異なる 2 つのクライアントが対話する場合、機能によっては一方のクライアントでは使用できても、他方のクライアントでは使用できないことがあります。 Skype for Business Server に含まれる機能を最も有効に利用し、全体的なユーザー エクスペリエンスを向上させるために、クライアント バージョン フィルターを使用して、環境で使用されるクライアント バージョンを制限できます。 クライアント バージョン フィルターを使用すると、複数バージョンのクライアントをサポートすることによって発生するコストを抑えることもできます。

## <a name="tasks-you-can-perform"></a>実行できるタスク

[**クライアント バージョン ポリシー**] ページでは、次のタスクを実行できます。

- 既定の (グローバル) **クライアント** バージョン ポリシーを編集します。

- 特定のサイトまたはプールのクライアント バージョン ポリシーを作成する。

- 個別のユーザーに割り当てることのできるクライアント バージョン ポリシーを作成する。

> [!NOTE]
> 匿名ユーザーをユーザー、サイト、またはサービスに関連付けることはできないため、匿名ユーザーが影響を受けるのはグローバル レベルのポリシーだけです。

## <a name="ui-reference"></a>UI リファレンス

次の一覧に、このページのメニュー、コマンド、フィールド、およびプロパティを示します。

- **New** 次のクライアント バージョン ポリシーのそれぞれを 1 つ以上作成できます。

  - サイト ポリシー

  - プール ポリシー

  - ユーザー ポリシー

- **編集** クライアント バージョン ポリシーのオプションを変更できます。 このオプションを使用すると、次の操作を実行できます。

  - **詳細の表示** このオプションは、クライアント バージョン ポリシーのオプションを変更できるダイアログ ボックスを開きます。

  - **[すべて選択]** このオプションは、リスト内のすべてのクライアント バージョン ポリシーを選択します。

  - **削除** このオプションは、選択したクライアント バージョン ポリシーをすべて削除します。

- **更新** クライアント バージョン ポリシーの一覧を更新して、すべてのクライアント バージョン ポリシーのオプションの状態を確認できます。

クライアントとクライアント バージョン間の相互運用性の詳細については、「計画」のドキュメントの [「クライアント相互](/previous-versions/office/lync-server-2013/lync-server-2013-client-interoperability-in-lync-2013) 運用性」を参照してください。 クライアント バージョン ポリシーの操作の詳細については、「操作」のドキュメントの「[Specify the Client Versions Supported in Your Organization](/previous-versions/office/lync-server-2013/lync-server-2013-specifying-the-client-applications-that-can-be-used-to-log-on-to-lync-server-2013)」を参照してください。