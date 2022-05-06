---
title: 電話会議の PIN の長さを設定する
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: b86d31c6-1543-478f-b8c6-4b71e708403a
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
description: PIN の長さと要件のパラメーターについて説明し、Microsoft Teamsの会議の長さを設定する方法について説明します。
ms.openlocfilehash: c08be6e0bd66677c1459cb829dc21c749efceffd
ms.sourcegitcommit: 8f999bd2e20f177c6c6d8b174ededbff43ff5076
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/15/2022
ms.locfileid: "62055887"
---
# <a name="set-the-pin-length-for-audio-conferencing-meetings-in-microsoft-teams"></a>Microsoft Teams で電話会議用の PIN の長さを設定する

Microsoft Teamsの電話会議を設定すると、電話会議ブリッジが表示されます。 電話会議ブリッジには 1 つまたは複数の電話番号を含めることができます。 設定した電話番号は、Microsoft Teams アプリの会議出席依頼に含まれます。
  
電話会議ブリッジは、電話を使用して会議にダイヤルインしようとしているユーザーの呼び出しに応答します。 自動応答からの音声プロンプトで発信者に応答し、設定に応じて通知を再生し、発信者に名前の記録を求めることができます。 **Microsoft ブリッジ設定** を使用すると、会議の通知と会議参加エクスペリエンスの設定を変更し、会議の開催者が使用する PIN の長さを設定できます。 会議の開催者は、Microsoft Teams アプリを使用して会議に参加できない場合、PIN を使用して会議を開始します。

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="setting-the-pin-length"></a>PIN の長さを設定する

Microsoft Teams管理センターの使用:

1. 左側のナビゲーションで、[**会議**]  >  [**会議ブリッジ**] に移動します。

2. [**会議ブリッジ**] ページの最上部で、[**ブリッジの設定**] をクリックします。

3. **[ブリッジ設定**] ウィンドウの [**PIN の長さ**] で、PIN に必要な桁数を選択します。

4. **[保存]** をクリックします。

> [!NOTE]
> PIN は会議 ID とは異なります。 会議 ID は、会議に参加するときに呼び出し元によって使用されます。 会議を識別するために使用されます。 PIN は、会議の開催者として呼び出し元を認証するために使用されます。

## <a name="want-to-know-more-about-pin-settings"></a>PIN 設定の詳細を知りたいですか?

- PIN は 4 ~ 12 桁です。既定値は 5 です。 数値は PIN の作成時にのみ使用されます。 文字と特殊文字は使用されません。

- PIN は、Microsoft Teams ユーザーがまだ会議を開始していない場合にのみ、会議の開催者に必要です。 全員が会議にダイヤルインしている場合、会議の開催者が会議を開始するには PIN が必要です。

- PIN セキュリティ設定は、Microsoft ブリッジに関連付けられているすべての電話番号に適用されます。 特定のブリッジに関連付けられている電話番号を使用するすべての会議に適用されます。

## <a name="want-to-know-more-about-windows-powershell"></a>Windows PowerShell の詳細情報

Windows PowerShellはすべて、ユーザーの管理と、ユーザーの許可または許可されていない操作です。 Windows PowerShellを使用すると、1 つの管理ポイントを使用してMicrosoft 365またはOffice 365を管理できます。複数のタスクがある場合に毎日の作業を簡略化できます。 Windows PowerShell の使用を開始するには、次のトピックを参照してください。

- [Windows PowerShell で Office 365 を管理するための最善の方法](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)

- [Windows PowerShell で Microsoft 365 または Office 365 を管理するための最善の方法](/previous-versions//dn568025(v=technet.10))

Windows PowerShell の詳細については、「[Microsoft Teams PowerShell のリファレンス](/powershell/module/teams/?view=teams-ps)」をご覧ください。

## <a name="related-topics"></a>関連トピック

[Microsoft 365またはOffice 365での電話会議の試用または購入](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)
