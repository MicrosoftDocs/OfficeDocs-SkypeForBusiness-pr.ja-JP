---
title: 電話会議の自動応答の言語を設定する
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 26d73dda-ab26-4af4-8aec-d17f3479ae50
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-mar2020
description: Microsoft Teams で電話会議番号の電話会議の自動応答言語を選択する方法について説明します。
ms.openlocfilehash: 0a27015fefe8c290f8e122f5d9edf46aa3c8583f
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117185"
---
# <a name="set-auto-attendant-languages-for-audio-conferencing-in-microsoft-teams"></a>Microsoft Teams で電話会議の自動案内の言語を設定する

Microsoft Teams の電話会議自動応答では、会議に参加するときに、さまざまな言語で音声の発信者に挨拶を行います。
  
第 1 言語 1 つと、第 2 言語 4 つまで選びます。設定する第 1 言語が最初に使用され、第 2 言語は選択した順に自動応答で使用されます。 
  
> [!NOTE]
>  変更できるのは、専用カテゴリの電話会議番号の言語のみです。 共有電話会議番号の言語は変更できません。

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="set-the-conferencing-auto-attendant-languages"></a>電話会議の自動応答の言語を設定する

![Microsoft Teams ロゴを示すアイコン](media/teams-logo-30x30.png) **Microsoft Teams 管理センターを使用する**

1. 左側のナビゲーションで、[**会議**]  >  [**会議ブリッジ**] に移動します。

2. 一覧 **から専用** の電話会議の電話番号を選び、ページの上部にある [編集] をクリック **します**。 専用の電話会議番号の言語のみを変更できます。 [ **編集** ] オプションは、専用の電話会議番号が選択されている場合にのみ表示されます。

3. 右側のウィンドウで、使用する既定の言語と別の言語を選択します。 
 
    > [!NOTE]
    > サポートされる既定の言語と代替言語が一覧表示されます。 リストで言語を選択する順序は、発信者に表示される言語の順序です。 

4. [ **保存**] をクリックします。

    
## <a name="want-else-should-i-know"></a>その他の情報

- 電話会議でサポートされる言語のリストを確認するには、「[ダイヤルイン会議でサポートされる言語](/SkypeForBusiness/audio-conferencing-in-office-365/audio-conferencing-supported-languages)」をご覧ください。
    
- 専用電話番号には言語を設定できますが、共有電話番号には設定できません。
    
- Microsoft をプロバイダーとして使用して Microsoft 365 または Office 365 の電話会議を利用できる国/地域の一覧については[](phone-numbers-for-audio-conferencing-in-teams.md)、「電話会議の電話番号」を参照してください。
    
## <a name="want-to-use-windows-powershell"></a>Windows PowerShell を使用する場合

詳細については、[Microsoft Teams PowerShell のリファレンス](/powershell/module/teams/?view=teams-ps)をご覧ください。
  
## <a name="related-topics"></a>関連項目

[Microsoft 365 または Office 365 で電話会議を試用または購入する](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)