---
title: 組織の電話番号のリストを表示する
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.assetid: 93098bc5-df63-4a1f-8734-0b72a6280a69
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Calling Plans
- seo-marvel-mar2020
description: Microsoft Teams 管理センターを使用して、組織内のすべての電話番号と、ユーザーに割り当てられているか割り当てられていないすべての電話番号の一覧を表示する方法について説明します。
ms.openlocfilehash: 41eceb3618fae61308b90a88165ce1935ad6b30b
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117235"
---
# <a name="see-a-list-of-phone-numbers-in-your-organization"></a>組織の電話番号のリストを表示する

Microsoft 365 の電話会議や Office 365 の電話会議など、ユーザーや他のサービス (サービス番号) に割り当て可能な電話番号には、さまざまな種類Officeがあります。
  
## <a name="to-see-a-list-of-all-phone-numbers-that-you-have-for-your-organization"></a>組織のすべての電話番号のリストを表示するには

![Microsoft Teams 管理センターを使用する ](media/teams-logo-30x30.png) **Teams ロゴを示すアイコン**

1. Microsoft Teams 管理 **センターに移動します**。

2. In the left navigation, go to **Voice** > **Phone numbers**.

    > [!IMPORTANT]
    > Skype for Business 管理センターの左のナビゲーションに [**音声**] オプションが表示されるようにするには、最初に **Enterprise E5 ライセンス**、**電話システム** アドオン ライセンス、または **電話会議** アドオン ライセンスを少なくとも 1 件購入する必要があります。

3. 割り当てられている電話番号を表示するには、[状態] 列 **を参照** してください。

4. ビューにフィルターを適用するには、フィルター アイコンをクリックします。 [フィルター **]** ウィンドウでは、ドロップダウン リストを使用して、次の方法でビューをフィルター処理できます。

   - **設定した数値** 範囲。 最も小さい数値または最大の数値で検索できます。

   - 指定した数値で始まる数値。

   - 番号 **のライセンス認証の状態**。

   - 数値 **の種類**。

   - 電話番号の **状態**。

## <a name="to-see-all-of-the-phone-numbers-that-are-assigned-to-users"></a>ユーザーに割り当てられているすべての電話番号を表示するには

ユーザーを設定する場合、ユーザーに既に割り当てられている電話番号と、ユーザーに割り当て可能な電話番号の一覧を表示したい場合があります。
  
![Microsoft Teams 管理センターを使用する ](media/teams-logo-30x30.png) **Teams ロゴを示すアイコン**

1. Microsoft Teams 管理 **センターに移動します**。

2. In the left navigation, go to **Voice** > **Phone numbers**.

    > [!IMPORTANT]
    > Microsoft Teams 管理センターの左側のナビゲーションに音声オプションを表示するには、最初に Enterprise **E5** ライセンス、電話システム アドオンライセンス、または電話会議アドオン ライセンスを 1 つ以上購入する必要があります。

3. 割り当てられている番号をすばやく並べ替え、割り当てられている番号を確認するには、[ **状態]** 列見出しをクリックします。 または、フィルター アイコンをクリックし、ビューをフィルター処理して、ユーザーに既に割り当てられている電話番号や、ユーザーに割り当て可能な割り当てられていない番号を表示できます。 以下の分類でフィルターすることができます。

   - **ユーザーに割り当て済み**

   - **会議ブリッジに割り当て済み** 

   - **未割り当て**

## <a name="to-see-the-phone-numbers-that-are-assigned-to-voice-users"></a>音声ユーザーに割り当てられているすべての電話番号を表示するには

組織内のユーザーに電話の送受信を設定する場合は、まず電話番号を取得してから、ユーザーに割り当てる必要があります。 電話番号を取得した後は、番号の割り当てのライセンス認証の状態を確認したい場合があります。

![Microsoft Teams 管理センターを使用する ](media/teams-logo-30x30.png) **Teams ロゴを示すアイコン** !
  
1. Microsoft Teams 管理 **センターに移動します**。

2. In the left navigation, go to **Voice** > **Phone numbers**.

    > [!IMPORTANT]
    > Microsoft Teams 管理センターの左側のナビゲーションに音声オプションを表示するには、最初に Enterprise **E5** ライセンス、電話システム アドオンライセンス、または電話会議アドオン ライセンスを 1 つ以上購入する必要があります。

3. [アクティブ化] 状態でビューをフィルターするには、フィルター アイコンをクリック **します** 。次の条件でフィルター処理できます。

   - **アクティブ化**

   - **課題の保留中**

   - **課題が失敗しました**

   - **更新プログラムの保留中**

   - **更新に失敗しました**

## <a name="using-the-teams-powershell-module"></a>Teams PowerShell モジュールを使用する

Teams PowerShell モジュールを使用して前のセクションから同じ情報を取得できますが、バージョン 1.1.6 以降 (Skype for Business Online コネクタの統合を含む) が必要です。 モジュールの詳細については [、「Microsoft Teams PowerShell の概要」を参照してください](teams-powershell-overview.md)。

[Get-CsOnlineTelephoneNumber](/powershell/module/skype/get-csonlinetelephonenumber)コマンドレットを使用すると、組織のすべての電話番号の一覧を表示できます。 たとえば、次のコマンドを実行して、各電話番号とその状態を表示できます。

```PowerShell
Get-CsOnlineTelephoneNumber | ft Id,ActivationState
```

[Get-CsOnlineUser](/powershell/module/skype/get-csonlineuser)コマンドレットを使用すると、ユーザーに割り当てられているすべての電話番号を表示できます。 たとえば、次のコマンドを実行して、電話番号が割り当てられているすべてのユーザーを表示できます。

```PowerShell
Get-CsOnlineUser | Where-Object  { $_.LineURI -notlike $null } | ft DisplayName,UserPrincipalName,LineURI
```

## <a name="related-topics"></a>関連項目
[電話番号の移行に関するよくある質問](./phone-number-calling-plans/port-order-overview.md)

[通話プランで使用されるさまざまな種類の電話番号](./different-kinds-of-phone-numbers-used-for-calling-plans.md)

[組織の電話番号を管理する](/microsoftteams/manage-phone-numbers-for-your-organization)

[緊急通話の利用条件](./emergency-calling-terms-and-conditions.md)

[緊急通話の免責事項ラベル](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

[Get-CsOnlineTelephoneNumber](/powershell/module/skype/get-csonlinetelephonenumber)
  
[Get-CsOnlineUser](/powershell/module/skype/get-csonlineuser)