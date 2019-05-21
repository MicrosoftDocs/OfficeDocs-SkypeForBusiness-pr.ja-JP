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
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Skype for Business Onlineでダイヤルイン会議の番号を検索する方法。 '
ms.openlocfilehash: 220d266796dc52832e3f10fe45ca6e9f2e999e14
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34299051"
---
# <a name="see-a-list-of-audio-conferencing-numbers-in-skype-for-business-online"></a>Skype for Business Onlineの電話会議の番号の一覧を見る

> [!NOTE]
> Microsoft Teams会議の番号については、  [「Microsoft Teams会議の番号の一覧を見る」](/MicrosoftTeams/see-a-list-of-audio-conferencing-numbers-in-teams) を参照してください。

Skype for Businessユーザー向けの電話会議を設定すると、電話会議に参加できる電話番号を観覧することができます。　 あなたの組織に連絡可能な電話会議のすべての電話番号がリストに追加されます。
  
 **価格を見る** 「[電話会議の価格を確認する」を](https://products.office.com/en-us/skype-for-business/audio-conferencing#Requirements)参照してください。
  
> [!IMPORTANT]
> **電話会議のすべてのダイヤルイン番号のリストを含んでいるリソースはありません。** お住まいの地域または国/地域で利用可能なダイヤルイン電話番号があるかどうかを確認する場合は、 **Skype for business 管理センター** > **音声** > **電話番号**に移動し、[**追加**]、[**新しいサービス] の順にクリックします。数値**。 [**国/地域**]、[**都道府県/地域**]、[**市区町村**] のリストを使用して、検索をフィルタします。 また、有料サービスの電話番号をお探しの場合は、「**都道府県/地域**」リストから**無料通話**を選択してください。
  
組織内で連絡可能な電話番号が1つのみの場合、その番号がすべてのユーザーの既定値の番号として使用されます。 複数の電話番号で連絡可能な場合は、各ユーザーが既定値の電話番号を選択することができます。 この既定の番号は、 Skype for Businessの会議招待状に含まれます。
  
1 人のユーザーのダイヤルイン番号を変更するには、 [「招待状にある電話番号を設定する」](set-the-phone-numbers-included-on-invites.md) を参照してください。
  
> [!NOTE]
> 国内のダイヤルイン番号は組織専用で、既定値の電話番号として設定することができる唯一の番号です。 ただし、海外のダイヤルイン番号は、複数の組織間で共有することができます。 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="to-view-your-audio-conferencing-phone-numbers"></a>電話会議の電話番号を表示するには

1. 職場または学校のアカウントを使用して、Office 365 にサインインします。
    
2. Go to the **Office 365 admin center** > **Skype for Business**.
    
3. **Skype for business 管理センター**の左のナビゲーションで、[**電話会議** > の**Microsoft bridge**] に移動し、次の操作を行います。
    
   - 電話会議で利用可能な電話番号を表示することができます。
    
   - また、場所を表示したり、電話会議の自動応答で使用する第1言語と第2言語を表示したりすることもできます。
    
> [!NOTE]
> **電話会議** > **ユーザー**に移動し、ユーザーのプロパティを選択して、組織で利用可能な電話番号の一覧から新しい番号を選択して、既定の番号を変更することができます。 「[招待状に含まれている電話番号を設定する](set-the-phone-numbers-included-on-invites.md)」を参照してください。 

  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Windows PowerShell での管理方法について

- 時間を節約したり、自動化したりするには、 [set-csonlinedialinconferencingservicenumber](https://go.microsoft.com/fwlink/?LinkId=617691)コマンドレットを使用します。
    
- Windows PowerShell は、ユーザーと、ユーザーに許可されていることと許可されていないことを管理するためにあるということです。Windows PowerShell があれば、一元管理を使用して Office 365 を管理し、複数のタスクを抱えているときに、日常の仕事を簡素化することができます。Windows PowerShell を開始するには、これらのトピックを参照してください。
    
  - [Office 365 PowerShell を使用する必要がある理由](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Windows PowerShell で Office 365 を管理するための最善の方法](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- 多くのユーザーの設定を同時に変更するときなどは、Office 365 管理センターのみを使用するよりも、Windows PowerShell の方に、速度、わかりやすさ、生産性の点で多くのメリットがあります。 次のトピックで、これらの利点を説明します。
    
  - [Windows PowerShell と Skype for Business Online の概要](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Windows PowerShell による Skype for Business Online の管理](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Windows PowerShell を使用した一般的な Skype for Business Online の管理タスクの実行](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > Skype for Business Online 用の Windows PowerShell モジュールがあれば、Skype for Business Online に接続するリモートの Windows PowerShell セッションを作成できます。このモジュールは、64 ビット版のコンピューターでのみサポートされており、「[Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688)」の Microsoft ダウンロード センターからダウンロードできます。
  
## <a name="related-topics"></a>関連項目

[Office 365 での電話会議を試用または購入する](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
  
