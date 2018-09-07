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
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Skype for Business Onlineでダイヤルイン会議の番号を検索する方法。 '
ms.openlocfilehash: 118b929f16f0c6edf5c512ddc9b94529a34a8860
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2018
ms.locfileid: "23861151"
---
# <a name="see-a-list-of-audio-conferencing-numbers-in-skype-for-business-online"></a>Skype for Business Onlineの電話会議の番号の一覧を見る

> [!NOTE]
> Microsoft Teams会議の番号については、  [「Microsoft Teams会議の番号の一覧を見る」](/MicrosoftTeams/see-a-list-of-audio-conferencing-numbers-in-teams) を参照してください。

Skype for Businessユーザー向けの電話会議を設定すると、電話会議に参加できる電話番号を観覧することができます。　 あなたの組織に連絡可能な電話会議のすべての電話番号がリストに追加されます。
  
 **価格を見る** [「電話会議の価格」](https://products.office.com/en-us/skype-for-business/audio-conferencing#Requirements)を参照してください。
  
> [!IMPORTANT]
> **電話会議のすべてのダイヤルイン番号のリスティングを含んでいるリソースはありません。** ご利用のエリアまたは国や地域で利用可能なダイヤルイン電話番号があるかどうかを見るには、[**Skype for Business 管理センター**] > [**音声**] > [**電話番号**] に移動して、[**追加**] をクリックしてから [**新しいサービス番号**] をクリックします。 [**国/地域**]、[**都道府県/地域**]、[**市区町村**]のリストを使用して、検索をフィルタします。 また、フリーダイヤルのサービス番号を探している場合は、[**フリーダイヤル**] を [**国/地域**] リストから選択します。
  
組織内で連絡可能な電話番号が1つのみの場合、その番号がすべてのユーザーの既定値の番号として使用されます。 複数の電話番号で連絡可能な場合は、各ユーザーが既定値の電話番号を選択することができます。 この既定の番号は、 Skype for Businessの会議招待状に含まれます。
  
1 人のユーザーのダイヤルイン番号を変更するには、 [「招待状にある電話番号を設定する」](set-the-phone-numbers-included-on-invites.md) を参照してください。
  
> [!NOTE]
> 国内のダイヤルイン番号は組織専用で、既定値の電話番号として設定することができる唯一の番号です。 ただし、海外のダイヤルイン番号は、複数の組織間で共有することができます。 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="to-view-your-audio-conferencing-phone-numbers"></a>電話会議の電話番号を表示するには

1. 職場または学校のアカウントを使用して、Office 365 にサインインします。
    
2.  > **[Skype for Business]** の **[Office 365 管理センター]** に移動します。
    
3. ** Skype for Business 管理センター**のナビゲーション左側にある** [電話会議]** >  ** [Microsoft ** ブリッジ]へ移動します:

    
  - 電話会議で連絡可能な電話番号を表示することができます。
    
  - 位置の表示や、電話会議の自動応答で使用する第 1 言語と第 2 言語を表示することができます。
    
> [!NOTE]
> **[電話会議]** > **[ユーザー]** へ移動してユーザーの領域を選択し、組織内で連絡可能な番号の一覧から新しい番号を選択して既定値の番号を変更することができます [「招待状にある電話番号を設定する」](set-the-phone-numbers-included-on-invites.md)」を参照してください。 

  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Windows PowerShellで管理する方法

-  [GetCsOnlineDialInConferencingServiceNumber](https://go.microsoft.com/fwlink/?LinkId=617691) コマンドレットを使用して、時間を短縮または自動化することができます。
    
- Windows PowerShell は、ユーザーと、ユーザーに許可されていることと許可されていないことを管理するためにあるということです。Windows PowerShell があれば、一元管理を使用して Office 365 を管理し、複数のタスクを抱えているときに、日常の仕事を簡素化することができます。Windows PowerShell を開始するには、これらのトピックを参照してください。
    
  - [Windows PowerShell で Office 365 を管理するための最善の方法](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Windows PowerShell で Office 365 を管理するための最善の方法](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- 多くのユーザーの設定を同時に変更するときなどは、Office 365 管理センターのみを使用するよりも、Windows PowerShell の方に、速度、わかりやすさ、生産性の点で多くのメリットがあります。 次のトピックで、これらの利点を説明します。
    
  - [Windows PowerShell と Lync Online の概要](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Windows PowerShell による Skype for Business Online の管理](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [クイック リファレンス: Windows PowerShell を使用した一般的な Lync Online の管理タスクの実行](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > Windows PowerShell を使用した一般的な Skype for Business Online の管理タスクの実行[](https://go.microsoft.com/fwlink/?LinkId=294688)
  
## <a name="related-topics"></a>このモジュールは、64 ビットのコンピューターでのみサポートされ、Microsoft ダウンロード センターの「Skype for Business Online 用 Windows PowerShell モジュール」からダウンロードできます。

[Office 365 での電話会議を使用または購入する](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
  
