---
title: 通話プランの既知の問題
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.assetid: baa3645a-0518-472e-942e-971c63ba4ca0
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Calling Plans
description: PSTN 通話の通話プランの既知の問題とその対処方法について説明します。
ms.openlocfilehash: 3a97057f61c154ded83b85becbfcf53dc2b4bc78
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/13/2020
ms.locfileid: "44220737"
---
# <a name="calling-plans-known-issues"></a>通話プランの既知の問題

通話プランは、Skype for Business Online の新機能です。 次のような現在の問題が追跡され、積極的に調査されています。 今後のビルドで機能が更新されると、それらのメンバーは解決される可能性があります。
  
## <a name="calling-plans-known-issues"></a>通話プランの既知の問題

|**既知の問題**|**注釈**|
|:-----|:-----|
|技術プレビューのライセンスを、通話プランの運用ライセンスに移行しても、ライセンスが自動的に更新されることはありません。  <br/> |最初に新しいライセンスを購入して、ユーザーに割り当てる準備ができたことを確認します。 ユーザーからプロモーション (Tech Preview) ライセンスを削除し、新しい**国内通話プラン**または**国内および国際通話プラン**のライセンスをユーザーに**直ち**に割り当てます。 <br/> 複数のユーザーのライセンスを削除して追加する場合は、Windows PowerShell を使用しているすべてのユーザーからライセンスを削除し、Windows PowerShell を使用してすべてのユーザーのライセンスを**直ち**に割り当てることが非常に重要です。 こうすることで、大量のユーザーライセンスの割り当てを処理する際にサービスが中断されることがなくなります。 PowerShell スクリプトの例については、「 [Skype For business および Microsoft Teams のライセンスを割り当てる](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)」を参照してください。  <br/> **注:** ハイブリッドユーザー用にオンプレミスの PSTN 接続を使用している場合は、**電話システム**のライセンスを*割り当てる必要が*あります。 音声通話プランを割り当てることはでき**ません**。 ただし、microsoft 365 365 または office 365 の通話プランを有効にし365ている場合は、そのユーザーの**国内通話プラン**または**国内および国際通話プラン**のライセンスを割り当てる必要があります。 [Skype for Business と Microsoft Teams のライセンスを割り当てる](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)を参照してください。

> [!NOTE]
> その他の電話番号を取得する必要がある場合は、[ビジネス製品のサポートにお問い合わせください。管理者向けヘルプ](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)         |
   
## <a name="related-topics"></a>関連項目
[電話番号の移行に関するよくある質問](/microsoftteams/transferring-phone-numbers-common-questions)

[通話プランで使用されるさまざまな種類の電話番号](/MicrosoftTeams/different-kinds-of-phone-numbers-used-for-calling-plans)

[組織の電話番号を管理する](/microsoftteams/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization)

[緊急通話の利用条件](/microsoftteams/emergency-calling-terms-and-conditions)

[Skype for Business Online: 緊急通話の免責事項ラベル](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

  
 
