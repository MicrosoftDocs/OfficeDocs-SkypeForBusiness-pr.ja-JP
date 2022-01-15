---
title: 会議の入退出のお知らせをオンまたはオフTeams
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: f2c7b5ea-07b6-4b77-8023-bec9596fcc32
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
- seo-marvel-apr2020
description: 管理者は、会議中に入退出のお知らせをオンまたはオフにする方法Microsoft Teamsできます。
ms.openlocfilehash: a9dcaaabcaa31160e162ba2a2685a02d9e2397da
ms.sourcegitcommit: 8f999bd2e20f177c6c6d8b174ededbff43ff5076
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/15/2022
ms.locfileid: "62056017"
---
# <a name="turn-on-or-off-entry-and-exit-announcements-for-meetings-in-microsoft-teams"></a>Microsoft Teams で会議の入退室通知をオンまたはオフにする

Microsoft 365 または Office 365 で電話会議を設定すると、電話会議ブリッジが表示されます。 電話会議ブリッジには、ユーザーが Microsoft Teams の会議にダイヤルインするために使用する 1 つまたは複数の電話番号を含めることができます。
  
電話会議ブリッジは、電話機を使用して会議にダイヤルインしているユーザーの通話に応答します。 会議ブリッジは、まず会議の自動応答の音声プロンプトで呼び出し元に応答します。設定によっては、次に通知を再生、呼び出し元に名前を記録するよう依頼し、PIN セキュリティをセットアップします。 PIN は Microsoft Teams の会議の開催者に付与され、Microsoft Teams アプリを使用して会議を開始することができない場合に、PIN で会議を開始することができます。 ただし、会議を開始するのに PIN を必要としないように設定することができます。

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="setting-meeting-join-options-using-the-microsoft-teams-admin-center"></a>管理センターで会議参加オプションMicrosoft Teams設定する

これらの変更を行うには、Teams サービス管理者であることが必要です。 「[Teams 管理者ロールを使用してチームを管理する](./using-admin-roles.md)」をご覧いただき、管理者ロールとアクセス許可を取得する方法について読んでください。

1. 管理センターにログインします。

2. 左側のナビゲーションで、[**会議**]  >  [**会議ブリッジ**] に移動します。

3. [**会議ブリッジ**] ページの最上部で、[**ブリッジの設定**] をクリックします。

4. [**ブリッジ設定**] ウィンドウで、[**会議の開始と終了の通知**] を有効または無効にします。 これは既定では選択されています。 この選択をクリアすると、既に参加済みのユーザーは、誰かが入ってきたり退出したりしたときに通知を受け取りません。

5. [**エントリ/退出のお知らせの種類**] の下にある [**名前または電話番号**] または [**トーン**] を選択します。

   > [!NOTE]
   > 既定では、外部参加者はダイヤルインされた参加者の電話番号を表示されません。 これらの電話番号のプライバシーを維持したい場合は、**開始/終了のお知らせの種類** の **トーン** を選びます (これにより、数字が Teams によって読み上げられません)。

6. [**名前または電話番号**] を選ぶ場合は、[**発信者に、会議に参加する前に自分の名前を記録するように要求します**] を有効または無効にします。

7. [**保存**] をクリックします。

## <a name="want-to-know-more-about-windows-powershell"></a>Windows PowerShell を使い始めるには、次のトピックを参照してください。

Windows PowerShellは、ユーザーの管理と、ユーザーが許可または許可されていない操作に関するすべてです。 このWindows PowerShell、単一の管理ポイントを使用して Microsoft 365 または Office 365 を管理し、複数のタスクを実行する場合に毎日の作業を簡略化できます。 Windows PowerShell の使用を開始するには、次のトピックを参照してください。

- [PowerShell または PowerShell をMicrosoft 365するOffice 365理由](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)

- [アプリを使用してMicrosoft 365またはOffice 365を管理Windows PowerShell](/previous-versions//dn568025(v=technet.10))

Windows PowerShell の詳細については、「[Microsoft Teams PowerShell のリファレンス](/powershell/module/teams/?view=teams-ps)」をご覧ください。
  
## <a name="related-topics"></a>関連トピック

[電話会議に関するよくある質問](audio-conferencing-common-questions.md)
