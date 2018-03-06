---
title: "組織での電話会議の動的 ID の使用"
ms.author: tonysmit
author: tonysmit
manager: scotv
ms.date: 11/17/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.custom:
- Adm_O365_FullSet
- Strat_SB_PSTN
ms.assetid: e55e4bff-fb67-4389-8695-f03024baa9b6
description: "電話会議サービスは、Skype for Business 会議および Microsoft Teams 会議ごとに別の会議 ID が提供されるように更新中です。動的会議 ID は、静的会議 ID を超える重要な改善です。以下を提供しています。"
---

# 組織での電話会議の動的 ID の使用

電話会議サービスは、Skype for Business 会議および Microsoft Teams 会議ごとに別の会議 ID が提供されるように更新中です。動的会議 ID は、静的会議 ID を超える重要な改善です。以下を提供しています。
  
- **セキュリティの強化** 会議 ID は Skype for Business 会議または Microsoft Teams 会議ごとに一意で、会議がスケジュールされると生成されます。
    
- **連続した会議および隣り合った会議向けのエクスペリエンスの向上** 単一の開催者の会議には、特定のダイヤルイン情報が提供されます。これにより、会議が相互に連続してスケジュールされている場合に、1 つの会議の電話参加者を別の会議の参加者と区別できるようになります。
    
- **シームレスな移行** 組織が動的会議 ID に対して有効化されている場合でも、静的会議 ID ですでに組織でスケジュールされているすべての会議はそのまま有効です。
    
> [!TIP]
> 動的 ID は、 **電話会議**に対して有効で、電話会議プロバイダーとして Microsoft を設定したユーザーにのみ使用可能です。ユーザーに対し [Microsoft を電話会議プロバイダーとして割り当てる](assign-microsoft-as-the-audio-conferencing-provider.md)ことが可能です。 
  
## 組織のユーザーに対する変更点について

動的会議 ID が組織に対して有効化されている場合、電話会議に有効な組織内のユーザーによってスケジュールされる新しい Skype for Business 会議または Microsoft Teams 会議に会議 ID が提供されます。これは、以前の静的会議 ID とは異なります。これまでに静的会議 ID を所有していた組織は、会議に参加するユーザーに対し、会議に参加する前に会議の出席依頼で新しい会議 ID を使用する必要があることを通知する必要があります。
  
> [!NOTE]
> 組織が動的会議 ID に対して有効化される前にユーザーによって静的会議 ID でスケジュールされている会議についてはそのまま静的会議 ID が使用されるため、何の影響もなく続けて会議をスケジュールできます。 
  
次の例に、同じユーザーによって編成された 2 つの Skype for Business 会議の会議 ID がそれぞれ異なる場合の新しいエクスペリエンスを示します。
  
 **会議 #1** は 9:00 AM から 10:00 AM までスケジュールされ、会議 ID は 93907123 です。
  
![First Dynamic Conference ID.](../images/997b2473-7645-46df-9774-95eb070c2239.png)
  
 **会議 #2** は同じユーザーによって 10:00 AM から 11:00 AM までスケジュールされ、会議 ID は 16353789 です。
  
![Second Dynamic Conference IDs](../images/e1eecc76-812b-426c-90e8-80e9f6f4ad31.png)
  
## 関連トピック

- [Skype for Business Online のセットアップ](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)
    
- [Skype for Business および Microsoft Teams の電話会議のセットアップ](set-up-audio-conferencing-for-skype-for-business-and-microsoft-teams.md)
    
- [Skype for Business と Microsoft Teams のアドオン ライセンス](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)
    

