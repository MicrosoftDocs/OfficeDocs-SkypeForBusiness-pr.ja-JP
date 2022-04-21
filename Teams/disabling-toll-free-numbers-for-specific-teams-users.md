---
title: 特定の Teams ユーザーの無料電話番号を無効にする
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-mar2020
description: 電話会議ブリッジ会議で開催者がフリーダイヤル番号を使用する方法を制御する方法について説明します。
ms.openlocfilehash: 6d841a48381609a019a1749095aac4a95901a7c4
ms.sourcegitcommit: 296fbefe0481c0b8b94aee925118474375cdf138
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/21/2022
ms.locfileid: "65016629"
---
# <a name="disabling-toll-free-numbers-for-specific-teams-users"></a>特定の Teams ユーザーの無料電話番号を無効にする

組織の Microsoft 電話会議ブリッジに無料電話番号がある場合、特定の開催者の会議でその使用を許可または禁止することができます。  

既定では、組織内のすべてのユーザーは、無料電話番号を使用することができます。つまり、それらの番号が使用可能な場合は、会議に参加するために参加者が使用できます。 この設定が組織の特定のユーザーに対しては必要ない場合、特定のユーザーが会議でそれらの番号を使用するのを無料電話番号有効化コントロールを使って制限できます。

特定の開催者の無料電話番号が無効になっている場合:

- 対象の開催者が招待する会議で無料電話番号は含まれなくなります。
- 無料電話番号は、対象の開催者が招待する会議で参照される [電話番号の検索] ページにリストされなくなります。
- 参加者は、組織の無料電話番号をダイヤルしてその開催者の会議に参加できなくなります。
- 参加者は、電話番号 (有料) を使用して対象開催者の会議に引き続き参加できます。

## <a name="disabling-toll-free-numbers-for-specific-users"></a>特定のユーザーの無料電話番号を無効にする

特定のユーザーのフリーダイヤル番号を無効にするには、それらのユーザーに割り当てられている *TeamsAudioConferencingPolicy* 内で *AllowTollFreeDialIn* の設定を **オフ** に変更します。 無効にすると、そのようなユーザーによって作成された新しい会議には無料電話番号は含まれません。 [有料電話番号とフリーダイヤル番号の電話会議ポリシー設定](audio-conferencing-toll-free-numbers-policy.md) の詳細については、以下をご覧ください。

> [!IMPORTANT]
> 以前および以前にスケジュールされた定期的な会議では、フリーダイヤル番号が表示される場合があり、参加者はフリーダイヤル番号を使用してそのような会議に参加することはできません。 これらのユーザーの古い定期的な会議のスケジュールを変更し、MMS を使用して無料の電話番号を削除できます。

> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
