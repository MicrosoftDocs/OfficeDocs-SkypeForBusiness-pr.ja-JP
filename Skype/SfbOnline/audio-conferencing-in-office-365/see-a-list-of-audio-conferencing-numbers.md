---
title: "電話会議番号の一覧を参照してください。"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 2d6b4ed4-e12b-4691-8405-fae720d69425
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
description: "Skype for Business 内から会議にダイヤルイン番号を調べる方法について説明します。 "
ms.openlocfilehash: 3417a103e59638690d2ee100fa88a9671f3b0d44
ms.sourcegitcommit: 2d84f687ccc44220d5ec9d8b429dfae65cced5a7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/01/2018
---
# <a name="see-a-list-of-audio-conferencing-numbers"></a>電話会議番号の一覧を参照してください。

設定すると音声会議をセットアップする Skype for Business および Microsoft チームのユーザーに対して、電話会議用に利用できる電話番号を表示することができます。すべての組織に利用できる電話会議の電話番号が一覧表示されます。
  
 **価格をお探しですか?**[電話会議の価格](https://products.office.com/en-us/skype-for-business/audio-conferencing#Requirements)を参照してください。
  
> [!IMPORTANT]
> **電話会議のすべてのダイヤルイン番号の一覧を含むリソースがない**。ないか確認ダイヤルイン電話番号利用可能な領域または国/地域を検索する場合は、 **Skype for Business 管理センター**に移動 > **音声** > **電話番号**を**追加**] をクリックし、**新しいサービス数値**します。**国/地域**、**状態/地域のリストを使用して**、および**市区町村**の検索がフィルターされます。また、サービスのフリー ダイヤル番号を探している場合は**フリー ダイヤル**から、**状態/地域を選びます**] ボックスの一覧です。
  
1 つだけの電話番号が、組織内で提供されている場合、として使用されます、既定の番号のすべてのユーザー。複数の電話番号が使用できる場合は、ユーザーごとに既定の電話番号を選択することができます。この既定の番号は、ビジネスや Microsoft チーム会議出席依頼の Skype に含まれます。
  
1 人のユーザーのダイヤルイン電話番号を変更するのには[携帯電話への招待に含まれる数値の設定](set-the-phone-numbers-included-on-invites.md)を確認できます。
  
> [!NOTE]
> 国内ダイヤルイン番号は組織専用、既定の電話番号として設定できるだけで、です。ただし、国際ダイヤルイン番号は、複数の組織で共有することがあります。 
  
## <a name="to-view-your-audio-conferencing-phone-numbers"></a>電話会議電話番号を表示するには

1. 職場または学校のアカウントで Office 365 にサインインします。
    
2. **Office 365 管理センター**に移動 > **Skype for Business**します。
    
3. **Skype for Business 管理センター**、左のナビゲーションで**電話会議**に移動 > **Microsoft ブリッジ**し。
    
  - 電話会議を利用できる電話番号を表示することができます。
    
  - 場所を表示することもできます。 電話会議で使用されるプライマリおよびセカンダリ言語の自動応答する.
    
> [!NOTE]
> **電話会議**に移動できる > **ユーザー**と既定値を変更するのには、ユーザーのプロパティは、組織で利用可能な番号の一覧から新しい番号を選択し、番号を選択します。[携帯電話への招待に含まれる数値の設定](set-the-phone-numbers-included-on-invites.md)を参照してください。 
  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Windows PowerShell で管理する方法を知りたいとしていますか。

- 時間を節約し、自動化したりには、 [Get CsOnlineDialInConferencingServiceNumber](https://go.microsoft.com/fwlink/?LinkId=617691)コマンドレットを使用することができます。
    
- Windows PowerShell がユーザーを管理するユーザーを許可または使用できません。Windows PowerShell で複数のタスクを実行するがある場合、日常業務を簡素化する管理の 1 つのポイントを使用して Office 365 を管理できます。Windows PowerShell で開始するには、次のトピックを参照してください。
    
  - [Office 365 PowerShell を使用する必要がある理由](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Windows PowerShell で Office 365 を管理する最善の方法](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell では多くの利点速度、わかりやすいように、および生産性でのみ実行しようとする設定の変更、多くのユーザーに一度になど、Office 365 管理センターを使用します。次のトピックでこれらの利点について学習します。
    
  - [Windows PowerShell と Skype for Business Online の概要](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Windows PowerShell を使用して、Skype for Business Online の管理するには](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Windows PowerShell を使用して、共通の Skype for Business Online の管理タスクを実行するには](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > Skype for Business Online 用の Windows PowerShell モジュールを使用すると、Skype for Business Online に接続するリモートの Windows PowerShell セッションを作成することができます。このモジュールでは、64 ビット コンピューター以外では、Microsoft ダウンロード センターからダウンロードできます[Skype for Business Online 用の Windows PowerShell モジュール](https://go.microsoft.com/fwlink/?LinkId=294688)。
  
## <a name="related-topics"></a>関連トピック

[Skype for Business とチームの Microsoft の音声会議をセットアップする設定します。](set-up-audio-conferencing.md)
  

