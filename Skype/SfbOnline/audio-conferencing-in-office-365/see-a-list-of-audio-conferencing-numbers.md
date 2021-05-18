---
title: Skype for Business Onlineの電話会議の番号の一覧を見る
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 2d6b4ed4-e12b-4691-8405-fae720d69425
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: 'Skype for Business Onlineでダイヤルイン会議の番号を検索する方法。 '
ms.openlocfilehash: dfb9e0acc57019fa64b6233b37272eb7901f4dc7
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/06/2021
ms.locfileid: "52236983"
---
# <a name="see-a-list-of-audio-conferencing-numbers-in-skype-for-business-online"></a>Skype for Business Onlineの電話会議の番号の一覧を見る

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

> [!NOTE]
> Microsoft Teams会議の番号については、  [「Microsoft Teams会議の番号の一覧を見る」](/MicrosoftTeams/see-a-list-of-audio-conferencing-numbers-in-teams) を参照してください。

Skype for Businessユーザー向けの電話会議を設定すると、電話会議に参加できる電話番号を観覧することができます。　 あなたの組織に連絡可能な電話会議のすべての電話番号がリストに追加されます。
  
 **価格を見る** 「 [電話会議の価格」を参照してください](https://products.office.com/skype-for-business/audio-conferencing#Requirements)。
  
> [!IMPORTANT]
> **電話会議のすべてのダイヤルイン番号のリストを含んでいるリソースはありません。** 地域または国/地域で使用できるダイヤルイン電話番号が表示される場合は **、Skype for Business 管理** センターの [Voice  >    >  **電話 Numbers]** に移動し、[追加] をクリックし、[新しいサービス番号] をクリックします。 [**国/地域**]、[**都道府県/地域**]、[**市区町村**] のリストを使用して、検索をフィルタします。 また、無料のサービス番号をお探しの場合は、[状態/地域] の一覧から [無料 **通話] を選択** します。
  
組織内で連絡可能な電話番号が1つのみの場合、その番号がすべてのユーザーの既定値の番号として使用されます。 複数の電話番号で連絡可能な場合は、各ユーザーが既定値の電話番号を選択することができます。 この既定の番号は、 Skype for Businessの会議招待状に含まれます。
  
1 人のユーザーのダイヤルイン番号を変更するには、 [「招待状にある電話番号を設定する」](set-the-phone-numbers-included-on-invites.md) を参照してください。
  
> [!NOTE]
> 国内のダイヤルイン番号は組織専用で、既定値の電話番号として設定することができる唯一の番号です。 ただし、海外のダイヤルイン番号は、複数の組織間で共有することができます。 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="to-view-your-audio-conferencing-phone-numbers"></a>電話会議の電話番号を表示するには

1. 仕事用または学校用のアカウントでサインインします。
    
2. [管理センター] に移動 **> Skype for Business。**
    
3. [Skype for Business **センター] の** 左側のナビゲーションで、[**電話会議**] [Microsoft Bridge] に移動し、次の  >  操作を行います。
    
   - 電話会議で使用できる電話番号を表示できます。
    
   - また、場所と、電話会議の自動応答で使用されるプライマリ言語とセカンダリ言語を表示できます。
    
> [!NOTE]
> [電話会議ユーザー **]** に移動し、ユーザーのプロパティを選択して既定の番号を変更するには、組織内の利用可能な番号の一覧から新しい番号  >  を選択します。 「[招待状に含まれている電話番号を設定する](set-the-phone-numbers-included-on-invites.md)」を参照してください。 

  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Windows PowerShell での管理方法について

- 時間を節約したり、自動化したりするには [、Get-CsOnlineDialInConferencingServiceNumber コマンドレットを使用](/powershell/module/skype/Get-CsOnlineDialInConferencingServiceNumber) できます。
    
- Windows PowerShellは、ユーザーの管理と、ユーザーが許可または許可されていない操作についてすべて行います。 このWindows PowerShell、1 つの管理Microsoft 365またはOffice 365を管理し、複数のタスクを実行する場合に毎日の作業を簡略化できます。 Windows PowerShell の使用を開始するには、次のトピックを参照してください。
    
  - [PowerShell で使用する必要があるMicrosoft 365またはOffice 365理由](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - [アプリを使用してMicrosoft 365またはOffice 365を管理Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
- Windows PowerShell多くのユーザーに対して一度に設定を変更する場合など、Microsoft 365 管理センターのみを使用する場合に、速度、シンプルさ、生産性に多くの利点があります。 次のトピックで、これらの利点を説明します。
    
  - [Windows PowerShell と Skype for Business Online の概要](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [Windows PowerShell による Skype for Business Online の管理](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [Windows PowerShell を使用した一般的な Skype for Business Online の管理タスクの実行](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
    > [!NOTE]
    > Skype for Business Online 用の Windows PowerShell モジュールがあれば、Skype for Business Online に接続するリモートの Windows PowerShell セッションを作成できます。このモジュールは、64 ビット版のコンピューターでのみサポートされており、「[Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688)」の Microsoft ダウンロード センターからダウンロードできます。
  
## <a name="related-topics"></a>関連項目

[電話会議を試用または購入するには、Microsoft 365またはOffice 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
