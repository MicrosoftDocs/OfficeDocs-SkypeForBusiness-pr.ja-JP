---
title: Microsoft Teams でのチームの期限切れと更新
author: LanaChin
ms.author: v-lanac
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: abgupta
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
description: チームの有効期限と更新について説明し、Microsoft 365 グループの有効期限ポリシーを使用して、Microsoft Teams で使用されていないチームを自動的にクリーンアップする方法について説明します。
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: 697e36085169e0666e6a821a66c763be39cf9425
ms.sourcegitcommit: 6a4bd155e73ab21944dd5f4f0c776e4cd0508147
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/24/2020
ms.locfileid: "44868524"
---
# <a name="team-expiration-and-renewal-in-microsoft-teams"></a>Microsoft Teams でのチームの期限切れと更新

多くのチームがいる組織には、実際には使用されない teams が多いことがよくあります。 これは、製品の実験、短期的なチームのコラボレーション、または組織を離れるチーム所有者など、いくつかの理由で発生する可能性があります。 時間の経過と共に、チームはテナントリソースを蓄積して、負担を作ることができます。  

使用されていないチームの数を管理者として指定するには、 [Microsoft 365 グループの有効期限ポリシー](https://docs.microsoft.com/microsoft-365/admin/create-groups/office-365-groups-expiration-policy)を使って、使用していないチームを自動的にクリーンアップすることができます。 Teams はグループによってサポートされているため、グループの有効期限ポリシーはチームにも自動的に適用されます。

チームに有効期限ポリシーを適用すると、チームの所有者は、チームの有効期限の30日、15日間、1日前にチームの更新の通知を受け取ります。 チーム所有者は通知を受信したときに、チームの設定で [**今すぐ更新**] をクリックして、チームを更新することができます。

![チーム設定でチームを更新するための [今すぐ更新] ボタンのスクリーンショット](media/team-expiration.png "チーム設定でチームを更新するための [今すぐ更新] ボタンのスクリーンショット")

チーム所有者がチームを更新しない場合は、チームは "ソフト削除" 状態になります。つまり、この状態は、次の30日以内に復元できます。

## <a name="team-auto-renewal"></a>チームの自動更新

更新が期限切れになった場合に、チーム所有者がチームの更新を忘れてしまった可能性があります。 これらのシナリオでは、チームに適用される有効期限ポリシーが原因で、アクティブな使用中のチームが削除される可能性があります。  

誤って削除されるのを防ぐため、自動更新はグループの有効期限ポリシーのチームに対して自動的に有効になります。 グループの有効期限ポリシーが設定されると、チーム所有者から手動での介入なしに、少なくとも1つのチームメンバーからのチャネルアクセスを持つすべてのチームが自動的に更新されます。

## <a name="known-issues"></a>既知の問題

**チームの有効期限と、基になるグループが一致しない**

チームを更新する前に、チームをバックアップするグループが最初に更新されます。 更新の一部として、グループに新しい有効期限が設定され、将来の日付になります。 この新しい日付は、Teams にすぐに表示されない可能性があります。 同期には最大24時間かかることがあります。チームとその基になるグループの有効期限の間に不一致がある場合は、24時間待ってからさらにサポートを求めます。
