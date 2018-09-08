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
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Skype for Business Onlineでダイヤルイン会議の番号を検索する方法。 '
ms.openlocfilehash: 43442d2ecee1de30126b73dd7cce8124db650c84
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/08/2018
ms.locfileid: "23891258"
---
# <a name="see-a-list-of-audio-conferencing-numbers-in-skype-for-business-online"></a>Skype for Business Onlineの電話会議の番号の一覧を見る

> [!NOTE]
> Microsoft Teams会議の番号については、  [「Microsoft Teams会議の番号の一覧を見る」](/MicrosoftTeams/see-a-list-of-audio-conferencing-numbers-in-teams) を参照してください。

Skype for Businessユーザー向けの電話会議を設定すると、電話会議に参加できる電話番号を観覧することができます。　 あなたの組織に連絡可能な電話会議のすべての電話番号がリストに追加されます。
  
 **価格を見る** [オーディオ会議の価格](https://products.office.com/en-us/skype-for-business/audio-conferencing#Requirements)を参照してください。
  
> [!IMPORTANT]
> **電話会議のすべてのダイヤルイン番号のリストを含んでいるリソースはありません。** かどうかダイヤルインの電話番号では、領域または国/地域を表示する検索する場合に、**ビジネス管理センターの Skype** > **音声** > **の電話番号**を**追加**] をクリックし、**新しいサービス番号**です。 [**国/地域**]、[**都道府県/地域**]、[**市区町村**] のリストを使用して、検索をフィルタします。 また、サービスのフリー ダイヤル番号を検索する場合は、**フリー ダイヤル**から**の状態または地域を選択**の一覧です。
  
組織内で連絡可能な電話番号が1つのみの場合、その番号がすべてのユーザーの既定値の番号として使用されます。 複数の電話番号で連絡可能な場合は、各ユーザーが既定値の電話番号を選択することができます。 この既定の番号は、 Skype for Businessの会議招待状に含まれます。
  
1 人のユーザーのダイヤルイン番号を変更するには、 [「招待状にある電話番号を設定する」](set-the-phone-numbers-included-on-invites.md) を参照してください。
  
> [!NOTE]
> 国内のダイヤルイン番号は組織専用で、既定値の電話番号として設定することができる唯一の番号です。 ただし、海外のダイヤルイン番号は、複数の組織間で共有することができます。 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="to-view-your-audio-conferencing-phone-numbers"></a>電話会議の電話番号を表示するには

1. 職場または学校のアカウントを使用して、Office 365 にサインインします。
    
2. ** [Office 365 管理センター] ** > ** [Skype for Business]** に移動します。
    
3. **電話会議**には、**ビジネス管理センターの Skype**、左側のナビゲーションでの > **マイクロソフトのブリッジ**をし。
    
  - オーディオ会議で使用可能な電話番号を表示することができます。
    
  - 場所を表示することもでき、オーディオ会議で使用されるプライマリとセカンダリの言語の自動アテンダントです。
    
> [!NOTE]
> **オーディオ会議**に移動することができます > **ユーザー**と組織内の利用可能な番号の一覧から新しい番号を選択することによって番号の既定値を変更するのにはユーザーのプロパティ] を選択します。 「[出席依頼に含まれている会議の開催者のために電話会議の電話番号を設定する](set-the-phone-numbers-included-on-invites.md)」をご覧ください。 

  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Go to the Office 365 admin centerSkype for Business.

- 時間を短縮または、これを自動化するには、 [Get CsOnlineDialInConferencingServiceNumber](https://go.microsoft.com/fwlink/?LinkId=617691)コマンドレットを使用することができます。
    
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
  
