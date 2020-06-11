---
title: Teams での会議の入場および退出のお知らせを有効または無効にする
ms.author: tonysmit
author: tonysmit
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
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-apr2020
description: 管理者は、Microsoft Teams 会議で入力および終了のお知らせを有効または無効にする方法について説明します。
ms.openlocfilehash: 824949ea1c212f514830dfad3926444944ac099c
ms.sourcegitcommit: 1807ea5509f8efa6abba8462bce2f3646117e8bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/10/2020
ms.locfileid: "44690983"
---
# <a name="turn-on-or-off-entry-and-exit-announcements-for-meetings-in-microsoft-teams"></a>Microsoft Teams で会議の入退室通知をオンまたはオフにする

Microsoft 365 または Office 365 で電話会議をセットアップするときに、電話会議ブリッジが提供されます。 電話会議ブリッジには、ユーザーが Microsoft Teams の会議にダイヤルインするために使用する 1 つまたは複数の電話番号を含めることができます。 
  
電話会議ブリッジは、電話機を使用して会議にダイヤルインしているユーザーの通話に応答します。 会議ブリッジは、まず会議の自動応答の音声プロンプトで呼び出し元に応答します。設定によっては、次に通知を再生、呼び出し元に名前を記録するよう依頼し、PIN セキュリティをセットアップします。 PIN は Microsoft Teams の会議の開催者に付与され、Microsoft Teams アプリを使用して会議を開始することができない場合に、PIN で会議を開始することができます。 ただし、会議を開始するのに PIN を必要としないように設定することができます。

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="setting-meeting-join-options"></a>会議の参加オプションの設定

![Microsoft Teams ロゴを示すアイコン](media/teams-logo-30x30.png) **Microsoft Teams 管理センターを使用する**

これらの変更を行うには、管理者である必要があります。

1. 管理センターにログイン  <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> します。

2. 左側のナビゲーションで、[**会議**]  >  [**会議ブリッジ**] に移動します。 

3. [**会議ブリッジ**] ページの最上部で、[**ブリッジの設定**] をクリックします。 

4. [**ブリッジ設定**] ウィンドウで、[**会議の開始と終了の通知**] を有効または無効にします。 これは既定では選択されています。 この選択をクリアすると、既に参加済みのユーザーは、誰かが入ってきたり退出したりしたときに通知を受け取りません。
    
5. [**エントリ/退出のお知らせの種類**] の下にある [**名前または電話番号**] または [**トーン**] を選択します。

   > [!NOTE]
   > 既定では、外部参加者はダイヤルイン参加者の電話番号を表示することはできません。 これらの電話番号のプライバシーを維持する場合は、[アナウンスの**種類**] の [**トーン**] を選択します (これにより、チームがこの番号を閲覧できなくなります)。
    
6. [**名前または電話番号**] を選ぶ場合は、[**発信者に、会議に参加する前に自分の名前を記録するように要求します**] を有効または無効にします。
    
7. [**保存**] をクリックします。

## <a name="want-to-know-more-about-windows-powershell"></a>Windows PowerShell の詳細情報

Windows PowerShell では、ユーザーの管理と、許可または許可されていないユーザーの操作について説明します。 Windows PowerShell を使用すると、複数のタスクがある場合に、1つの管理ポイントを使用して Microsoft 365 または Office 365 を管理し、日常業務を簡素化することができます。 Windows PowerShell の使用を開始するには、次のトピックを参照してください。
    
  - [Microsoft 365 または Office 365 PowerShell を使用する必要がある理由](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Windows PowerShell を使用して Microsoft 365 または Office 365 を管理するのに最適な方法](https://go.microsoft.com/fwlink/?LinkId=525142)
    
Windows PowerShell の詳細については、「[Microsoft Teams PowerShell のリファレンス](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)」をご覧ください。
  
## <a name="related-topics"></a>関連トピック

[電話会議に関するよくある質問](audio-conferencing-common-questions.md)
