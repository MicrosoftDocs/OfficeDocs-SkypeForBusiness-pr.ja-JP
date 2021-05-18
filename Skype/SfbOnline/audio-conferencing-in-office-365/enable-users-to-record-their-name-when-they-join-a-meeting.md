---
title: ユーザーが Skype for Business Online で会議に参加するときに自分の名前を記録Skype for Businessする
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 1d649328-ada7-422d-a074-d6da4da36970
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
description: Skype for Business Online で会議に参加するときに、ユーザーが自分の名前を記録できるかどうかを有効または無効にする方法についてSkype for Businessします。
ms.openlocfilehash: ee6ae85946453d6065a6473ec331b93e4509ebc9
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/06/2021
ms.locfileid: "52237313"
---
# <a name="enable-users-to-record-their-name-when-they-join-a-meeting-in-skype-for-business-online"></a>ユーザーが Skype for Business Online で会議に参加するときに自分の名前を記録Skype for Businessする

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

> [!Note]
> ユーザーが自分の名前を Teams に記録できるようにする必要がある場合は、「[Microsoft Teams で会議に参加するときにユーザーが自分の名前を記録できるようにする](/MicrosoftTeams/enable-users-to-record-their-name-when-they-join-a-meeting-in-teams)」を参照してください。

Microsoft 365 または Office 365 で電話会議を設定すると、電話番号と電話会議ブリッジと呼ばれるものが届く。 会議ブリッジには、1 つ以上の電話番号を含め、専用の電話番号または共有電話番号を使用できます。
  
ユーザーが電話を使って会議にダイヤルインすると、その通話は会議ブリッジによって応答されます。会議ブリッジでは、自動応答の音声プロンプトで発信者に応答してから、設定に応じて、お知らせを再生したり、発信者に名前を記録するように依頼したり、会議開催者の PIN セキュリティをセットアップしたりします。PIN が会議開催者に与えられて、開催者は会議を開始できるようになります。ただし、PIN がなくても会議を開始できるように設定できます。

## <a name="set-whether-callers-should-record-their-name"></a>呼び出し元が名前を記録するかどうかを設定する
    
1. **Skype for Business 管理センター** の左側のナビゲーション ウィンドウで、[**電話会議**]  >  [**Microsoft ブリッジ設定**] の順に移動します。
    
2. [ **会議参加エクスペリエンス**] の [ **会議の入退出の通知をオンにする**] で、次のいずれかを選びます。
    
   - **オン**: 発信者は、会議に参加する前に名前を記録するように依頼されます。 既定ではオンになっています。
    
   - **オフ**: 発信者は、会議に参加する前に名前を記録するように依頼されません。
    
3. 変更したら [ **保存**] をクリックします。
    
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Windows PowerShell で管理する方法

- 時間を節約したり、自動化したりするには [、Set-CsOnlineDialInConferencingTenantSettings コマンドレットを使用](/powershell/module/skype/Set-CsOnlineDialInConferencingTenantSettings) できます。
    
- Windows PowerShellは、ユーザーの管理と、ユーザーが実行できる操作についてすべて行います。 このWindows PowerShell、1 つの管理Microsoft 365またはOffice 365を管理し、複数のタスクを実行する場合に毎日の作業を簡略化できます。 Windows PowerShell の使用を開始するには、次のトピックを参照してください。
    
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
