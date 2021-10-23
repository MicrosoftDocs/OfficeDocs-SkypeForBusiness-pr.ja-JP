---
title: ユーザーが会議の名前を記録できる
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 1d649328-ada7-422d-a074-d6da4da36970
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-mar2020
description: ユーザーが会議に参加するときにユーザーが自分の名前を記録できるかどうかを有効または無効にする方法についてMicrosoft Teams。
ms.openlocfilehash: 4b78430ba3cc0d776176876235f2cefa5daa631d
ms.sourcegitcommit: 75adb0cc163974772617c5e78a1678d9dbd9d76f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2021
ms.locfileid: "60536698"
---
# <a name="enable-users-to-record-their-name-when-they-join-a-meeting-in-microsoft-teams"></a>Microsoft Teams でユーザーが会議に参加したときに自分の名前を記録できるようにする

Microsoft 365 または Office 365 で電話会議を設定すると、電話番号と電話会議ブリッジと呼ばれるものが届く。 会議ブリッジには、1 つ以上の電話番号を含め、専用の電話番号または共有電話番号を使用できます。
  
ユーザーが電話を使って会議にダイヤルインすると、その通話は会議ブリッジによって応答されます。会議ブリッジでは、自動応答の音声プロンプトで発信者に応答してから、設定に応じて、お知らせを再生したり、発信者に名前を記録するように依頼したり、会議開催者の PIN セキュリティをセットアップしたりします。PIN が会議開催者に与えられて、開催者は会議を開始できるようになります。ただし、PIN がなくても会議を開始できるように設定できます。

  
## <a name="set-whether-callers-should-record-their-name"></a>発信者が名前を記録するかどうかを設定する

 **Microsoft Teams 管理センターの使用**

1. 左側のナビゲーションで、[**会議**]  >  [**会議ブリッジ**] に移動します。 

2. [**会議ブリッジ**] ページの最上部で、[**ブリッジの設定**] をクリックします。 

3. 会議の入退出 **通知を有効または無効にします**。

4. 通知を有効にする場合は、[開始 **/** 終了のお知らせの種類] で [名前] または [電話番号] を選択し、[会議に参加する前に発信者に名前を記録する] を **オンにします。**

6. [**保存**] をクリックします。
    
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="want-to-know-more-about-windows-powershell"></a>Windows PowerShell の詳細情報

Windows PowerShellは、ユーザーの管理と、ユーザーが許可または許可されていない操作に関するすべてです。 このWindows PowerShell、1 つの管理Microsoft 365または Office 365 を管理できます。複数のタスクを実行する場合に毎日の作業を簡略化できます。 Windows PowerShell の使用を開始するには、次のトピックを参照してください。
    
  - [Windows PowerShell で Office 365 を管理するための最善の方法](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - [Windows PowerShell で Office 365 を管理するための最善の方法](/previous-versions//dn568025(v=technet.10))
    
Windows PowerShell の詳細については、「[Microsoft Teams PowerShell のリファレンス](/powershell/module/teams/?view=teams-ps)」をご覧ください。
  
## <a name="related-topics"></a>関連トピック

[電話会議を試用または購入する](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)