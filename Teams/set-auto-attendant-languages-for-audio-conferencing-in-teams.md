---
title: 電話会議の自動応答言語を設定する
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
description: '[電話会議] で電話会議の自動応答言語を選択する方法をMicrosoft Teams。'
ms.openlocfilehash: 0a27015fefe8c290f8e122f5d9edf46aa3c8583f
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117185"
---
# <a name="set-auto-attendant-languages-for-audio-conferencing-in-microsoft-teams"></a>Microsoft Teams で電話会議の自動案内の言語を設定する

会議の電話会議の自動応答Microsoft Teams会議に参加するときに、さまざまな言語で音声発信者にあいさつすることができます。
  
第 1 言語 1 つと、第 2 言語 4 つまで選びます。設定する第 1 言語が最初に使用され、第 2 言語は選択した順に自動応答で使用されます。 
  
> [!NOTE]
>  [専用] カテゴリの電話会議番号の言語のみを変更できます。 共有電話会議番号の言語は変更できません。

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="set-the-conferencing-auto-attendant-languages"></a>電話会議の自動応答の言語を設定する

![Microsoft Teams ロゴを示すアイコン](media/teams-logo-30x30.png) **Microsoft Teams 管理センターを使用する**

1. 左側のナビゲーションで、[**会議**]  >  [**会議ブリッジ**] に移動します。

2. 一覧 **から [専用** 電話会議の電話番号] を選択し、ページの上部にある [編集] を **クリックします**。 専用電話会議番号の言語を変更できるのは、その言語のみです。 [ **編集]** オプションは、[専用電話会議番号] が選択されている場合にのみ表示されます。

3. 右側のウィンドウで、必要な既定の言語と代替言語を選択します。 
 
    > [!NOTE]
    > サポートされている既定の言語と代替言語が一覧表示されます。 リストでそれらを選択する順序は、発信者に表示される言語の順序です。 

4. [ **保存**] をクリックします。

    
## <a name="want-else-should-i-know"></a>その他の情報

- 電話会議でサポートされる言語のリストを確認するには、「[ダイヤルイン会議でサポートされる言語](/SkypeForBusiness/audio-conferencing-in-office-365/audio-conferencing-supported-languages)」をご覧ください。
    
- 専用電話番号には言語を設定できますが、共有電話番号には設定できません。
    
- プロバイダーとして Microsoft を使用して Microsoft 365 または Office 365 の電話会議を利用できる国/地域の一覧については、「電話会議の 電話 番号」[を参照してください](phone-numbers-for-audio-conferencing-in-teams.md)。
    
## <a name="want-to-use-windows-powershell"></a>Windows PowerShell を使用する場合

詳細については、[Microsoft Teams PowerShell のリファレンス](/powershell/module/teams/?view=teams-ps)をご覧ください。
  
## <a name="related-topics"></a>関連トピック

[電話会議を試用または購入するには、Microsoft 365またはOffice 365](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)