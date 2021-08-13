---
title: 会議の構成
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.ConfMeetingSettingMain
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 24e8f749-d54c-4315-a8fe-bb9303b356ef
ROBOTS: NOINDEX, NOFOLLOW
description: 会議の構成設定では、ユーザーが作成できる会議の種類 (いわゆるmeetings) を定義し、匿名ユーザーとダイヤルイン会議ユーザーがこれらの会議に参加する方法 (またはかどうかを) 制御します。 これらの設定はスケジュール設定された会議にのみ適用されます。 クライアントで [今すぐ会議] オプションをクリックして作成されたアドホック会議には適用されません。
ms.openlocfilehash: c4c891b7ac058a5e206c8fcde2d30766f9f498fc342dd9cdd4c9b25564443dbc
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "54317642"
---
# <a name="meeting-configuration"></a>会議の構成

会議の構成設定では、ユーザーが作成できる会議 ("ミーティング" とも呼ばれます) の種類を定義でき、さらにこの会議への匿名ユーザーやダイヤルイン会議ユーザーの参加方法について (または、参加可能かどうかについて) 制御できます。 これらの設定はスケジュール設定された会議にのみ適用されます。 クライアントで [今すぐ会議] オプションをクリックして作成されたアドホック会議には適用されません。

会議の構成は、グローバル、サイト、またはプールのレベルで適用されます。

- **グローバル会議の構成:** グローバル会議の構成は既定で作成されます。 グローバルな会議の構成は編集できますが、削除することはできません。 グローバルな会議の構成の削除を試みると、設定がすべて既定値にリセットされます。

- **サイト会議の構成 (オプション):** 1 つ以上のサイト会議構成を作成できます。それぞれの構成は、特定のサイトに適用されます。 サイト構成は、グローバル構成を上書きします。

- **プール会議の構成 (オプション):** 1 つ以上のプール会議構成を作成できます。それぞれの構成は、特定のプールに適用されます。 プール構成は、グローバル構成とサイト構成を上書きします。

[**会議の構成**] ページには、組織で定義されているすべての会議の構成が一覧表示されます。

## <a name="tasks-you-can-perform"></a>実行できるタスク

[**会議の構成**] ページでは次のタスクを実行できます。

- 新しいサイトの会議の構成またはプールの会議の構成を作成する

- グローバルな構成または既存のサイトの構成またはプールの構成を変更する

- サイトの構成またはプールの構成を削除する

## <a name="ui-reference"></a>UI リファレンス

次の一覧に、このページのコマンドを示します。

- **New** 新しいサイト会議の構成またはプール会議の構成を開始します。

- **編集** 選択した会議の構成を開き、編集するか、リスト内のすべての会議構成を選択するか、選択したサイト構成またはプール構成を削除します。

    > [!NOTE]
    > グローバルな会議の構成に対して [**削除**] を使用すると、設定が既定値にリセットされます。

- **更新** 会議の構成の一覧を更新します。

次の一覧に、このページのフィールドを示します。

- **名前** 会議の構成を識別します。

- **スコープ** 会議構成のスコープを識別します。グローバル、サイト、またはプール。

会議の構成の操作の詳細については、「操作」のドキュメントの「[Create a or modify a Collection of Meeting Configuration Settings](/previous-versions/office/lync-server-2013/lync-server-2013-create-or-modify-a-collection-of-meeting-configuration-settings)」を参照してください。