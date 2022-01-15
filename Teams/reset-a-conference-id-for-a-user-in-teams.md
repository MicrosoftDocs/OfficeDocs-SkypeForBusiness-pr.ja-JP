---
title: Microsoft Teams でユーザーの会議 ID をリセットする
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 6e12242c-55f7-4bf4-90d7-0f36c0326b8e
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
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
description: Microsoft Teams でユーザーの会議 ID をリセットする手順と、会議の更新および移行ツールへのリンクを取得する手順について説明します。
ms.openlocfilehash: 55dc8935d191f518ca353d4b384b36e205f5c584
ms.sourcegitcommit: 8f999bd2e20f177c6c6d8b174ededbff43ff5076
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/15/2022
ms.locfileid: "62056047"
---
# <a name="reset-a-conference-id-for-a-user-in-microsoft-teams"></a>Microsoft Teams でユーザーの会議 ID をリセットする

動的な会議 ID は、発信者が会議にコールインするのに使用できるダイヤルイン番号と一緒に、会議出席依頼の下に含まれています。 ユーザーが電話番号をダイヤルするときに、発信者が会議に参加できるように、会議の自動応答は発信者にこの会議 ID の入力を求めます。
  
> [!NOTE]
> 電話会議 ID は自動的に生成され、7 ~ 9 桁の数字で、ユーザーの電話会議を有効にするときに設定されます。 **静的電話会議の IP はサポートされていません。**

## <a name="resetting-the-conference-id-for-a-user"></a>ユーザーの会議 ID のリセット

管理センター Microsoft Teams使用します。

1. 左側のナビゲーションで、[**ユーザー**] をクリックしてから、空いているユーザーのリストからユーザーを選択します。

2. [編集] **をクリックします**。

3. [電話 **会議] の [会議** ID の **リセット] をクリックします**。

4. [会議 **ID のリセット] ウィンドウで** 、[リセット] を **クリックします**。 A conference ID will be automatically created and an email sent to the user with the new conference ID. 既定では、メールはユーザーに送信されますが、オフにできます。

> [!NOTE]
> 会議 ID をリセットすると、新しい会議 ID を含むメールがユーザーに送信されます。 このメールは、プライマリ メール アドレス (多くの場合、ユーザーのメール アドレスまたはMicrosoft 365送信Office 365されます。 電子メールには、新しい会議 ID、既定のダイヤルイン電話番号、および既存の会議を更新するための手順が含まれている。
  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="what-else-should-i-know"></a>他に必要な情報はありますか?

- [電話会議] セクションでユーザーの [電子メールで会議情報を送信する] をクリックして、会議 IDとダイヤルイン電話番号を含むすべての会議情報をメールでユーザーに **送信できます。** PIN は送信されません。

- 7 ~ 9 桁の会議 ID は、Teamsされます。 長さを変更できない。

- 会議 ID をリセットすると、新しい会議 ID が [ **電話会議 ID**] に一覧表示されます。

- 新しい会議 ID が作成されると、古い会議 ID を使用してダイヤルインすることはできなくなります。 既存の会議の出席依頼のスケジュールを変更して、新しい会議 ID を出席依頼に追加するように、ユーザーに通知してください。

## <a name="want-to-know-more-about-windows-powershell"></a>Windows PowerShell の詳細情報

Windows PowerShellは、ユーザーの管理と、ユーザーが許可または許可されていない操作に関するすべてです。 このWindows PowerShell、1 つの管理Microsoft 365または Office 365 を管理し、複数のタスクを実行する場合に毎日の作業を簡略化できます。 Windows PowerShell の使用を開始するには、次のトピックを参照してください。

- [Windows PowerShell で Office 365 を管理するための最善の方法](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)

- [アプリを使用してMicrosoft 365またはOffice 365を管理Windows PowerShell](/previous-versions//dn568025(v=technet.10))

Windows PowerShell の詳細については、「[Microsoft Teams PowerShell のリファレンス](/powershell/module/teams/?view=teams-ps&preserve-view=true)」をご覧ください。

## <a name="related-topics"></a>関連トピック

[電話会議の PIN をリセットする](reset-the-audio-conferencing-pin-in-teams.md)
