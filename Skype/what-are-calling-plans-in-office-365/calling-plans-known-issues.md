---
title: "PSTN 通話の既知の問題"
ms.author: tonysmit
author: tonysmit
manager: scotv
ms.date: 11/14/2017
ms.audience: Admin
ms.topic: troubleshooting
ms.prod: office-online-server
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.custom: Adm_O365_FullSet
ms.assetid: baa3645a-0518-472e-942e-971c63ba4ca0

description: "Learn known issues with the calling plan for Office 365 (PSTN Calling) and what you can do about them. "
---

# PSTN 通話の既知の問題

PSTN 通話は Skype for Business Online の新機能です。現在追跡中で積極的に調査を行っている問題があり、Office 365 と Skype for Business Online の今後のビルドでこの機能が更新されるときに解決される可能性があります。下記にそれらの問題を記載します。
  
## PSTN 通話の既知の問題

|**既知の問題**|**コメント**|
|:-----|:-----|
|PSTN 通話の Tech Preview ライセンスを実稼働ライセンスに移行しても、ライセンスが自動的に更新されない。  <br/> |まず新しいライセンスを購入して、ユーザーに割り当てられるようにしてください。 プロモーション (Tech Preview) ライセンスをユーザーから削除してから、 **すぐに** 新しい Skype for Business Cloud PBX、Skype for Business PSTN 国内通話、または PSTN 国内/国際通話ライセンスをユーザーに割り当てます。 <br/> 複数のユーザーのライセンスを削除したり追加したりしている場合は、Windows PowerShell を使ってすべてのユーザーからライセンスを削除してから、すぐに Windows PowerShell を使ってライセンスをすべてのユーザーに割り当てることが非常に重要です。この操作を行うと、大量のユーザー ライセンスの割り当てを処理しているときに、サービスが中断されなくなります。PowerShell のサンプルのスクリプトについては、「[Skype for Business と Microsoft Teams のライセンスを割り当てる](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)」をご覧ください。  <br/> > [!CAUTION]> ハイブリッド ユーザーのオンプレミス PSTN 接続を使用している場合は、Skype for Business クラウド PBXライセンスのみを割り当てる必要があります。音声通話プランも割り当てる必要は **ありません** 。> ただし、Office 365 のユーザー用に PSTN 通話を有効にする場合は、音声通話プラン ライセンスを割り当てる必要があります。詳細については 「[Skype for Business と Microsoft Teams のライセンスを割り当てる](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)」をご覧ください。           |
   
## 関連項目

#### 

[緊急通話の利用条件](emergency-calling-terms-and-conditions.md)
  
[音声会議無料ダイヤルアウト期間](../accessibility-and-regulatory/audio-conferencing-complimentary-dial-out-period.md)

