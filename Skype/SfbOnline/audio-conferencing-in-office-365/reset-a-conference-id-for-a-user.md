---
title: "ユーザーの会議 ID をリセットします。"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 6e12242c-55f7-4bf4-90d7-0f36c0326b8e
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
description: "ユーザーを再設定する手順は会議 ID、会議の更新と移行ツールの会議へのリンクを取得するかを説明します。 "
ms.openlocfilehash: ba76f3afb5d92dadc66d09e07aa16d3589f57e4d
ms.sourcegitcommit: 2d84f687ccc44220d5ec9d8b429dfae65cced5a7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/01/2018
---
# <a name="reset-a-conference-id-for-a-user"></a>ユーザーの会議 ID をリセットします。

組織動的会議 Id を有効にされていない、プロバイダーとして Microsoft を使って音声会議に Skype for Business または Microsoft チームのユーザーが有効にすると、静的会議 ID が自動的に作成します。この会議 ID が会議出席依頼と発信者が会議にコールインするのに使用できるダイヤルイン電話番号の下部に含まれています。ユーザーは、電話番号をダイヤルするときに、会議の自動応答はに対して発信者を会議に参加ができるように、この会議 ID を入力を求められます。
  
> [!NOTE]
> 会議プロバイダーが Microsoft の場合は、ユーザーの会議 Id が既定で動的のみ] に設定されています。残念ながら、Skype for Business 管理センター」または「Windows Powershell を使用してに変更することはできません。Microsoft サポートに連絡する必要があります。 
  
静的な Id は、組織内のユーザーをランダムな番号を保存したくない場合に使用します。特定の番号を選択したり、覚えやすいものを使用することができます。動的会議 Id を使用する場合各会議ユーザーのスケジュールが取得割り当て会議の一意の id。場合は、割り当てる静的会議 Id、[ここ](using-audio-conferencing-dynamic-ids-in-your-organization.md)ではなく動的します。
  
会議 Id が自動的に設定だけ Skype for Business や Microsoft チームのユーザーが電話会議用に有効に、電話会議プロバイダーとして Microsoft を使用してです。サードパーティ電話会議プロバイダー (ACP) を使用しているユーザーの会議 ID をリセットする必要がある場合は、[プロパティ] ページで、ユーザーの会議 ID を手動で入力する必要があります。
  
## <a name="resetting-the-conference-id-for-a-user"></a>ユーザーの会議 ID をリセットします。

1. 職場または学校のアカウントで Office 365 にサインインします。
    
2. **Office 365 管理センター**に移動 > **Skype for Business**します。
    
3. **Skype for Business 管理センター**では、**電話会議**をクリックします。 > **ユーザー**の場合は、は、ユーザーを選択し、[操作ウィンドウの [**電話会議 ID** **をリセット**する] をクリックします。
    
4. **会議 ID をリセットですか?**ウィンドウで、[**はい**] をクリックします。会議 ID が自動的に作成し、新しい会議 ID を持つユーザーに送信されたメール既定では、ユーザーにメールが送られますが、これを無効にできます。
    
    > [!NOTE]
    > 会議 ID をリセットすると後、新しい会議 ID を含む電子メールをユーザーに送信されます。このメールが送信、プライマリ メール アドレスに多くの場合、Office 365 メールボックス。電子メールには、新しい会議 ID、既定のダイヤルイン電話番号と Skype for Business 会議を更新するツールを使用して既存の会議を更新する手順が含まれています。 
  
## <a name="what-else-should-i-know"></a>他に必要な情報はありますか?

- 操作ウィンドウで、ユーザーの**会議情報を電子メールで送信する**] をクリックして、会議 ID とのダイヤルイン電話番号を含むメール内のユーザーには、すべての会議情報を送信できます。PIN も送信されません。
    
- 会議 ID を 7 つの数字とでは、Skype for Business 管理センター、または Windows PowerShell を使用して、その長さを変更することはできません。
    
- リセットすると後、は、[**電話会議 ID**にリストされた新しい会議 ID を表示できます。
    
- [**ユーザー** ] ページでユーザーを選択すると、[**電話会議**の [アクション] ウィンドウの下部にある電話会議のユーザーの会議 ID を表示できます。
    
- 新しい会議 ID を作成したら、発信者に応答して古い会議 ID を使用できません。既存ように招待状に ID が追加された新しい会議出席依頼を会議のスケジュールを変更するユーザーに通知する必要があります。ユーザーは、Skype for Business 会議のツールを使用して、既存の会議を更新することができます。ダウンロード、インストール、および Business Meeting Update Tool の Skype を実行する方法を参照してください。
    
  - [Skype for Business と Lync の meeting Update Tool](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4)
    
  - [Skype for Business をオンラインで会議の移行ツール (64 ビット)](https://go.microsoft.com/fwlink/?LinkID=626047)
    
  - [Skype for Business をオンラインで会議の移行ツール (32 ビット)](https://www.microsoft.com/en-us/download/details.aspx?id=54079)
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Windows PowerShell で管理する方法を知りたいとしていますか。

- Windows powershell となるはすべてを管理するユーザーとユーザーの許可または使用できません。Windows PowerShell で Office 365 と Skype for Business Online の複数のタスクを実行するがある場合、日常業務を簡素化する管理の 1 つのポイントを使用して管理できます。Windows PowerShell で開始するには、次のトピックを参照してください。
    
  - [Windows PowerShell と Skype for Business Online の概要](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Office 365 PowerShell を使用する必要がある理由](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell では多くの利点速度、わかりやすいように、および生産性でのみ実行しようとする設定の変更、多くのユーザーに一度になどの Office 365 管理センターを使用します。次のトピックでこれらの利点について学習します。
    
  - [Windows PowerShell で Office 365 を管理する最善の方法](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Windows PowerShell を使用して、Skype for Business Online の管理するには](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Windows PowerShell を使用して、共通の Skype for Business Online の管理タスクを実行するには](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a>関連トピック

[ユーザーの音声会議の PIN をリセットします。](reset-the-audio-conferencing-pin-for-a-user.md)
