---
title: チームの動的なメンバーシップの概要
author: jambirk
ms.author: jambirk
manager: serdars
ms.date: 10/10/2018
ms.topic: article
ms.service: msteams
search.appverid: MET150
description: AAD に基づく動的なチームのメンバーシップについて説明します。
localization_priority: Normal
MS.collection: Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6a98009237d6575e97705ae7a8eea4b444ac77a0
ms.sourcegitcommit: 044286f9dec2743a622bdaeac03469418cfdfa0d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/19/2018
ms.locfileid: "25682367"
---
# <a name="overview-of-dynamic-membership-for-teams"></a>チームの動的なメンバーシップの概要

マイクロソフトのチームでは、動的なメンバーシップを使用して Office 365 のグループに関連付けられているチームをサポートします。 動的なメンバーシップは、特定の Azure Active Directory (AAD) でのユーザー属性をチェックする 1 つまたは複数の規則によって定義される、チームのメンバーシップを有効にします。 ユーザーは自動的に追加または、ユーザー属性を変更したり、ユーザーが参加し、テナントのままにして、的確なチームを削除します。

ことができます、動的なメンバーシップを使用してセットアップ チームが特定のユーザーが組織内の cohorts。 可能なシナリオは次のとおりです。
- 病院では、通信をブロードキャストするには、看護師、医師、および外科医の個別のチームを作成できます。 これは、病院が一時の従業員に依存している場合に特に重要です。
- 大学では、頻繁に変更される、かつ付加的な教職員を含め、特定の大学内のすべての教職員のチームを作成できます。
- 航空会社は、(と同じように、火曜日の午後無停止でシカゴからアトランタへ) のフライトごとにチームを作成し、自動的に割り当てられている、頻繁に変化するクルーを希望しています。

この機能では、特定のチームのメンバーの更新プログラムを自動的に使用するとは、特定のメンバーシップを手動で管理するのではなく、条件のセットに基づいています。 これを行うには、Azure AD プレミアム P1 のライセンスが必要です。 と、チームのメンバーシップは、AAD プロパティのすべてのユーザーの[テナント管理者によって割り当てられた](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-dynamic-membership)テナントと管理者用のアカウントがある場合を提供できます。

マイクロソフトのチームに必要数分から 2 時間まで、Office 365 のグループをチームに反映すると、動的なメンバーシップの変更を反映するように。

> [!NOTE]
> チーム メンバーがチームの所有者ではない、ルールを定義できます。

## <a name="creating-and-managing-an-office-365-group-with-dynamic-membership"></a>作成し、動的なメンバーシップを使用して、Office 365 のグループを管理します。
テナント管理者としてログインしているときに、[動的グループを作成し状態を確認するの](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-create-rule)に指示します。 必要に応じて、 [Azure Active Directory のグループの動的メンバーシップの規則](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-dynamic-membership)を参照してください。

## <a name="create-a-new-team-with-your-o365-group"></a>O365 グループで新しいチームを作成します。

今すぐメンバーシップの変更を反映させるための時間を確保して、[マイクロソフトのチームにグループを既存の Office 365 の強化](enhance-office-365-groups.md)で説明したように、新しいチームを作成します。

## <a name="apply-dynamic-membership-to-an-existing-team"></a>動的なメンバーシップを既存のチームに適用します。

既存のチームを実行し、 [Azure Active Directory 内に動的に静的なグループ メンバーシップの変更](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-change-type)で説明するように動的なメンバーシップでは、変更もできます。

## <a name="changes-in-client-behavior"></a>クライアントの動作の変更

チームの動的なメンバーシップを有効にする、チームのクライアントでは、チームのメンバーの管理は実行されません。 メンバーを追加、メンバーの役割を編集、送信し結合の要求を承認およびチームのままにするためのオプションはすべて非表示にします。
