---
title: "組織で電話会議の動的な Id を使用します。"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: e55e4bff-fb67-4389-8695-f03024baa9b6
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business, Microsoft Teams
localization_priority: Normal
ROBOTS: None
f1keywords: None
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
description: "各 Skype は、さまざまな会議 Id を持つビジネスおよびマイクロソフトのチームの会議には、オーディオ会議サービスを更新しています。 提供するため静的会議 Id が大幅に向上が、動的な会議 Id:"
ms.openlocfilehash: 0838014e8a88d5e27b6bd84838ea105b9f75025a
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/15/2017
---
# <a name="using-audio-conferencing-dynamic-ids-in-your-organization"></a>組織で電話会議の動的な Id を使用します。

各 Skype は、さまざまな会議 Id を持つビジネスおよびマイクロソフトのチームの会議には、オーディオ会議サービスを更新しています。 提供するため静的会議 Id が大幅に向上が、動的な会議 Id:
  
- **強化されたセキュリティ**会議 Id は、ビジネスまたはマイクロソフトのチーム会議の各 Skype に固有し、会議が予定されている場合に生成されます。
    
- **連続した会議および隣り合った会議向けのエクスペリエンスの向上** 単一の開催者の会議には、特定のダイヤルイン情報が提供されます。これにより、会議が相互に連続してスケジュールされている場合に、1 つの会議の電話参加者を別の会議の参加者と区別できるようになります。
    
- **シームレスな移行** 組織が動的会議 ID に対して有効化されている場合でも、静的会議 ID ですでに組織でスケジュールされているすべての会議はそのまま有効です。
    
> [!TIP]
> 動的 Id のみユーザーが利用できるが有効になっている * * オーディオ会議 * * し、microsoft が自社のオーディオ会議プロバイダーとして設定します。 ユーザーの[オーディオ会議プロバイダーとしてのマイクロソフトの割り当て](assign-microsoft-as-the-audio-conferencing-provider.md)ができます。
  
## <a name="what-changes-will-the-users-in-my-organization-see"></a>どのような変更は自分の所属組織内のユーザーを参照してください。

動的な会議 Id が有効になって、組織、ビジネスまたはマイクロソフトのチームが会議のすべての新しい Skype の電話会議は会議 Id が異なる場合がありますがある可能な組織内のユーザーによってスケジュールは、静的な会議 ID が前にする必要があります。 静的が開催する前に会議 Id に参加する前に、会議の出席依頼に新しい会議 ID を使用する必要があります会議に参加するユーザーに通知する必要があります。
  
> [!NOTE]
> 組織が影響を及ぼすことがなく会議をスケジュールするのには、引き続き、静的な会議 Id を持つ Id は引き続き動的の会議の有効にする前に静的な会議 Id を持つユーザーによってスケジュールされている会議。 
  
これらの例は、同じユーザーによって編成されているビジネス ・ ミーティング用の 2 つの Skype の新しいエクスペリエンスを示していますが、両方が 2 つの異なる会議 Id: 
  
 **会議 #1** は 9:00 AM から 10:00 AM までスケジュールされ、会議 ID は 93907123 です。
  
![First Dynamic Conference ID.](../images/997b2473-7645-46df-9774-95eb070c2239.png)
  
 **会議 #2** は同じユーザーによって 10:00 AM から 11:00 AM までスケジュールされ、会議 ID は 16353789 です。
  
![Second Dynamic Conference IDs](../images/e1eecc76-812b-426c-90e8-80e9f6f4ad31.png)
  
## <a name="related-topics"></a>関連トピック

- [Skype for Business Online のセットアップ](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)
    
- [Skype for Business および Microsoft Teams の電話会議のセットアップ](set-up-audio-conferencing.md)
    
- [Skype for Business と Microsoft Teams のアドオン ライセンス](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)
    

