---
title: チームの有効期限と更新 (Microsoft Teams
author: HowlinWolf-92
ms.author: v-mahoffman
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: abgupta
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
description: チームの有効期限と更新、およびグループの有効期限ポリシー Microsoft 365使用して、チームの未使用のチームを自動的にクリーンアップする方法についてMicrosoft Teams。
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: 543678baf7604b4c7ea80a4c913ba8713ed841b2
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/08/2021
ms.locfileid: "60828440"
---
# <a name="team-expiration-and-renewal-in-microsoft-teams"></a>チームの有効期限と更新 (Microsoft Teams

チームの数が多い組織には、実際には使用しないチームが多い場合があります。 これは、製品の実験、短期的なチームコラボレーション、組織を離れるチーム所有者など、いくつかの理由が原因で発生する可能性があります。 時間が経過すると、このようなチームは蓄積し、テナント リソースに負担を生み出す可能性があります。  

未使用のチームの数を抑制するには、管理者としてグループの有効期限ポリシー Microsoft 365[](/microsoft-365/admin/create-groups/office-365-groups-expiration-policy)使用していないチームを自動的にクリーンアップできます。 チームはグループによってサポートされます。そのため、グループの有効期限ポリシーはチームにも自動的に適用されます。

有効期限ポリシーをチームに適用すると、チーム所有者は、チームの有効期限の 30 日前、15 日前、1 日前にチームの更新に関する通知を受け取ります。 チーム所有者は、通知を受け取った後、チーム設定で [今すぐ **更新** ] をクリックしてチームを更新できます。

![チーム設定でチームを更新する [今すぐ更新] ボタンのスクリーンショット。](media/team-expiration.png "チーム設定でチームを更新する [今すぐ更新] ボタンのスクリーンショット")

チーム所有者がチームを更新しない場合、有効期限ポリシーが終了するまでチームでそれ以上のアクティビティがない場合、チームは "ソフト削除" 状態になります。つまり、今後 30 日以内に復元できます。

## <a name="team-auto-renewal"></a>チームの自動更新

更新を忘れたか、更新期限が切れたときにチーム所有者がチームを更新できない場合があります。 このようなシナリオでは、アクティブに使用されているチームは、チームに適用される有効期限ポリシーのために削除される可能性があります。  

誤って削除されないように、グループの有効期限ポリシーでチームの自動更新が自動的に有効になります。 グループの有効期限ポリシーが設定されている場合、有効期限の前にチーム メンバーから少なくとも 1 つのチャネルがアクセスしているチームは、チーム所有者からの手動の介入なしに自動的に更新されます。

## <a name="known-issues"></a>既知の問題

**チームと基になるグループの有効期限が一致しない**

チームが更新される前に、チームをバックアップするグループが最初に更新されます。 更新の一環として、グループに将来の日付の新しい有効期限が設定されます。 この新しい日付は、すぐには表示されない場合Teams。 同期には最大 24 時間かかる場合があります。チームとその基になるグループの有効期限の間に不一致が表示される場合は、24 時間待ってサポートを受け取る必要があります。