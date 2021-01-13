---
title: Microsoft Teams でのチームの有効期限と更新
author: cichur
ms.author: v-cichur
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: abgupta
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
description: チームの有効期限と更新、および Microsoft 365 グループの有効期限ポリシーを使用して、Microsoft Teams で未使用のチームを自動的にクリーンアップする方法について説明します。
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: b111ddd6b874fef22a7d221f6eb932c4c14c7b70
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809407"
---
# <a name="team-expiration-and-renewal-in-microsoft-teams"></a>Microsoft Teams でのチームの有効期限と更新

チームの数が多い組織は、実際には使用しないチームを持つ場合が多い。 これは、製品の実験、チームの短期間の共同作業、または組織を離れるチーム所有者など、いくつかの理由が原因で発生する可能性があります。 時間が経過すると、このようなチームは蓄積し、テナント リソースに負担をかける可能性があります。  

使用されていないチームの数を抑制するには、管理者として [Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/create-groups/office-365-groups-expiration-policy) グループの有効期限ポリシーを使用して、使用されていないチームを自動的にクリーンアップできます。 チームはグループに基いので、グループの有効期限ポリシーはチームにも自動的に適用されます。

有効期限ポリシーをチームに適用すると、チームの所有者は、チームの有効期限の 30 日前、15 日前、1 日前にチーム更新の通知を受け取ります。 チームの所有者が通知を受け取った場合、チームの設定で [今すぐ更新] をクリックしてチームを更新できます。

![チーム設定でチームを更新する [今すぐ更新] ボタンのスクリーンショット](media/team-expiration.png "チーム設定でチームを更新する [今すぐ更新] ボタンのスクリーンショット")

チームの所有者がチームを更新しない場合、有効期限ポリシーが終了するまでチームでそれ以上のアクティビティがない場合、チームは "回復可能な削除" 状態になります。つまり、30 日以内に復元できます。

## <a name="team-auto-renewal"></a>チームの自動更新

更新を忘れたか、更新の期限が切れたため、チームの所有者がチームを更新できない場合があります。 これらのシナリオでは、アクティブに使用されているチームは、チームに適用される有効期限ポリシーのために削除される可能性があります。  

誤って削除されないように、グループの有効期限ポリシー内のチームに対して自動更新が自動的に有効になります。 グループの有効期限ポリシーが設定されている場合、有効期限前にチーム メンバーから少なくとも 1 つのチャネル 訪問があるチームは、チーム所有者による手動による介入なしで自動的に更新されます。

## <a name="known-issues"></a>既知の問題

**チームと基になるグループの有効期限が一致しない**

チームを更新する前に、チームをバックアップするグループが最初に更新されます。 更新の一環として、グループに将来の日付の新しい有効期限が設定されます。 この新しい日付は、Teams ですぐには表示されない場合があります。 同期には最大 24 時間かかる場合があります。チームとその基になるグループの有効期限に不一致がある場合は、さらにサポートを受け取る前に 24 時間待ちます。
