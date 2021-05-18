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
description: PSTN 通話の通話プランに関する既知の問題と、その方法について説明します。
ms.openlocfilehash: 9c660ee3b173f104e26816460db45c5bcf400837
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/06/2021
ms.locfileid: "52238023"
---
# <a name="calling-plans-known-issues"></a>通話プランの既知の問題

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

通話プランは、Skype for Business Online の新機能です。 現在追跡され、積極的に調査されている問題を次に示します。 将来のビルドで機能が更新された場合に解決される可能性があります。
  
## <a name="calling-plans-known-issues"></a>通話プランの既知の問題

|**既知の問題**|**注釈**|
|:-----|:-----|
|Tech Preview ライセンスから通話プランの実稼働ライセンスへの移行では、ライセンスは自動的に更新されません。  <br/> |新しいライセンスを最初に購入して、ユーザーに割り当てる準備が整います。 ユーザーからプロモーション (Tech Preview) ライセンスを削除し、直ちに新しい国内通話プランまたは国内通話プランまたは国内通話プランと国際通話プランのライセンスをユーザーに割り当てる。  <br/> 複数のユーザーのライセンスを削除して追加する場合は、Windows PowerShell を使用してすべてのユーザーからライセンスを削除し、Windows PowerShell を使用してすべてのユーザーのライセンスを直ちに割り当てる必要があります。 これにより、大量のユーザー ライセンス割り当てを処理するときにサービスの中断が発生しなくします。 PowerShell スクリプトのサンプルについては、「ライセンスの割り当[てとSkype for Business割りMicrosoft Teams参照してください](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)。  <br/> **注:** ハイブリッド ユーザーにオンプレミス PSTN 接続を使用している場合は、ライセンスを割り当てる **電話システムがあります。** 音声通話 **プラン** も割り当てない。 ただし、Microsoft 365 または Office 365 内のユーザーに対して Microsoft 365 または Office 365 で通話プランを有効にする場合は、それらのユーザーに国内通話プランまたは国内通話プランまたは国内通話プランと国際通話プラン ライセンスを割り当てる必要があります。 [Skype for Business と Microsoft Teams のライセンスを割り当てる](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)を参照してください。

> [!NOTE]
> これより多くの電話番号を取得する必要がある場合は、ビジネス製品のサポートにお問い合わせください [- 管理者向けヘルプ](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)         |
   
## <a name="related-topics"></a>関連項目
[電話番号の移行に関するよくある質問](/microsoftteams/transferring-phone-numbers-common-questions)

[通話プランで使用されるさまざまな種類の電話番号](/MicrosoftTeams/different-kinds-of-phone-numbers-used-for-calling-plans)

[組織の電話番号を管理する](/microsoftteams/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization)

[緊急通話の利用条件](/microsoftteams/emergency-calling-terms-and-conditions)

[Skype for Business Online: 緊急通話の免責事項ラベル](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

  
 
