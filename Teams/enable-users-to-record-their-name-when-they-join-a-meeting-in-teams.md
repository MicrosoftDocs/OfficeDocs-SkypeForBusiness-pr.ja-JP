---
title: ユーザーが会議の名前を記録できるようにする
ms.author: heidip
author: MicrosoftHeidi
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
description: Microsoft Teams で会議に参加するときに、ユーザーが自分の名前を記録できるかどうかを有効または無効にする方法について説明します。
ms.openlocfilehash: 8d626437d1e7dd04ce8b4f91428bfe22cc3aeb43
ms.sourcegitcommit: 5abfb6f1abe10b6d32cf6eb97a890cf3138ed0e6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2022
ms.locfileid: "67641728"
---
# <a name="enable-users-to-record-their-name-when-they-join-a-meeting-in-microsoft-teams"></a>Microsoft Teams でユーザーが会議に参加したときに自分の名前を記録できるようにする

Microsoft 365 またはOffice 365で電話会議を設定すると、電話番号と電話会議ブリッジと呼ばれる電話番号が表示されます。 会議ブリッジには、専用または共有の電話番号を使用できる 1 つ以上の電話番号を含めることができます。
  
ユーザーが電話を使って会議にダイヤルインすると、その通話は会議ブリッジによって応答されます。会議ブリッジでは、自動応答の音声プロンプトで発信者に応答してから、設定に応じて、お知らせを再生したり、発信者に名前を記録するように依頼したり、会議開催者の PIN セキュリティをセットアップしたりします。PIN が会議開催者に与えられて、開催者は会議を開始できるようになります。ただし、PIN がなくても会議を開始できるように設定できます。

## <a name="set-whether-callers-should-record-their-name"></a>呼び出し元が自分の名前を記録するかどうかを設定する

Microsoft Teams 管理センターの使用:

1. 左側のナビゲーションで、[**会議**]  >  [**会議ブリッジ**] に移動します。

2. [**会議ブリッジ**] ページの最上部で、[**ブリッジの設定**] をクリックします。

3. **会議の参加と終了の通知を** 有効または無効にします。

4. 通知を有効にする場合は、[**入力/終了のお知らせの種類**] で **[名前] または [電話番号**] を選択し、**会議に参加する前に発信者に名前を記録するように求める** をオンにします。

5. **[保存]** をクリックします。

> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="want-to-know-more-about-windows-powershell"></a>Windows PowerShell の詳細情報

Windows PowerShell は、ユーザーと、ユーザーに許可されていることと許可されていないことを管理するためにあります。Windows PowerShell があれば、一元管理を使用して Microsoft 365 または Office 365 を管理し、複数のタスクを抱えているときに、日常の仕事を簡素化することができます。Windows PowerShell を開始するには、これらのトピックを参照してください。

- [Office 365 PowerShell を使用する必要がある理由](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)

- [Windows PowerShell で Office 365 を管理するための最善の方法](/previous-versions//dn568025(v=technet.10))

Windows PowerShell の詳細については、「[Microsoft Teams PowerShell のリファレンス](/powershell/module/teams/?view=teams-ps)」をご覧ください。
