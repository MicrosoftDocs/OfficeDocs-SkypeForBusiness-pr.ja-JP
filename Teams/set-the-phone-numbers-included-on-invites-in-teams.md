---
title: マイクロソフトのチームでの携帯電話への招待に含まれている番号の設定します。
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 32954439-d365-4125-872f-b37466ecb035
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'マイクロソフトのチーム ミーティングに参加するのには呼び出し元の既定の電話番号を作成する手順を取得します。 '
ms.openlocfilehash: 20dfd4255cd41e9f5aebf419f77307b30fe40042
ms.sourcegitcommit: 30620021ceba916a505437ab641a23393f55827a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/15/2018
ms.locfileid: "26533296"
---
# <a name="set-the-phone-numbers-included-on-invites-in-microsoft-teams"></a>Microsfot Teams で招待状に含まれている電話番号を設定する

マイクロソフト チームの会議を作成して、電話を使用してその会議にダイヤルインするユーザーを許可し、組織内のユーザーを Office 365 での音声会議に使用できます。
  
会議ブリッジは、組織用のダイヤルイン電話番号のセットを提供します。これらの番号はすべて会議開催者が作成した会議に参加するために使用できますが、会議出席依頼にどの番号を含めるか選ぶことができます。
  
> [!NOTE]
> 会議主催者の会議出席依頼には、1 つの有料電話番号と 1 つの無料電話番号を含めることができますが、会議出席依頼の下部に、会議に参加するために使用できるダイヤルイン電話番号のすべての一覧を表示するリンクも記載されています。 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="initial-assignment-of-phone-numbers-that-are-included-in-the-meeting-invites-for-new-users"></a>会議に含まれている電話番号の最初の割り当ての新しいユーザーの招待します。

会議にも含まれている電話番号は、オーディオ会議は、既定の会議通話の電話番号と既定会議無料電話番号のユーザーの設定で定義された有効にするユーザーの招待します。 各設定を指定する有料電話番号と無料電話番号は、特定のユーザーの会議出席依頼に含まれます。 前述したように、各会議出席依頼には、1 つの有料電話番号が、1 つの省略可能なフリー ダイヤル番号および特定の会議に参加するのに使用できるすべてのダイヤルインの電話番号の完全な一覧を開くリンクが含まれます。

新しいユーザーの場合は、ユーザーがオーディオ会議サービスを有効にすると、ユーザーの Office 365 のプロファイルに設定されている国に基づく既定の会議の有料電話番号が割り当てられます。 ユーザーの国または地域に一致する会議ブリッジに有料電話番号がある場合は、その番号がユーザーの既定の電話番号として自動的に割り当てられます。 ない場合に、ユーザーの既定の電話番号として会議ブリッジの有料電話番号が既定値として定義されている番号が割り当てられます。  

オーディオ会議サービスを有効にすると、ユーザー、既定の有料電話番号とユーザーの無料電話番号はテナント管理者が各自の初期値から任意の時点で。

## <a name="set-or-change-the-default-audio-conferencing-phone-number-for-a-meeting-organizer-or-user"></a>設定または会議の開催者またはユーザーの既定の電話会議の電話番号を変更します。

![チーム ・ ロゴ ・ 30x30.png](media/teams-logo-30x30.png) ビジネス管理センターは、マイクロソフトのチームと Skype を使用してください。

1. 左側のナビゲーションでは、**ユーザー**] をクリックしてで使用可能なユーザーの一覧からユーザーを選択します。

    ![マイクロソフトのチームとビジネス管理センターの Skype のユーザーの選択を示しています](media/teamsselectusers.png)

2. ページの上部で、[**編集**] をクリックします。

    ![マイクロソフトのチームとビジネス管理センターの Skype での編集] をクリックします。](media/teamsedituser.png)

3. **オーディオ会議**の横にある [**編集**] をクリックします。 
    
    ![編集をクリックしてオーディオ会議](media/teamseditaudioconf.png)

4. **有料電話番号**や**フリー ダイヤル番号**のフィールドを使用すると、ユーザーの数を入力します。


> [!IMPORTANT]
> ユーザーの電話会議の設定を変更すると、マイクロソフトのチーム会議の定期的な予定と今後の更新し、出席者に送信する必要があります。 

## <a name="want-to-use-windows-powershell"></a>Windows PowerShell を使用する場合

Windows PowerShell は、ユーザーと、ユーザーに許可されていることと許可されていないことを管理するためにあるということです。Windows PowerShell があれば、一元管理を使用して Office 365 を管理し、複数のタスクを抱えているときに、日常の仕事を簡素化することができます。Windows PowerShell を開始するには、これらのトピックを参照してください。
    
  - [Windows PowerShell で Office 365 を管理するための最善の方法](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Windows PowerShell で Office 365 を管理するための最善の方法](https://go.microsoft.com/fwlink/?LinkId=525142)
    
Windows PowerShell の詳細については、「[Microsoft Teams PowerShell のリファレンス](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)」をご覧ください。 
  
    
## <a name="related-topics"></a>関連トピック

[Office 365 での電話会議を使用または購入する](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)
