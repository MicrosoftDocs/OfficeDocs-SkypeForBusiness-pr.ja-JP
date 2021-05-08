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
description: Microsoft Teams管理センターを使用して、組織内のすべての電話番号と、ユーザーに割り当てられている、または割り当てられていないすべての電話番号の一覧を表示する方法について学習します。
ms.openlocfilehash: 41eceb3618fae61308b90a88165ce1935ad6b30b
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117235"
---
# <a name="see-a-list-of-phone-numbers-in-your-organization"></a>組織の電話番号のリストを表示する

ユーザーや他のサービス (サービス番号) に割り当て可能な電話番号には、Microsoft 365 や Office 365 の電話会議などがあります。
  
## <a name="to-see-a-list-of-all-phone-numbers-that-you-have-for-your-organization"></a>組織のすべての電話番号のリストを表示するには

![管理センターを使用Teams ](media/teams-logo-30x30.png) **ロゴをMicrosoft Teamsアイコン**

1. 管理センター **にMicrosoft Teams移動します**。

2. In the left navigation, go to **Voice** > **Phone numbers**.

    > [!IMPORTANT]
    > Skype for Business 管理センターの左のナビゲーションに [**音声**] オプションが表示されるようにするには、最初に **Enterprise E5 ライセンス**、**電話システム** アドオン ライセンス、または **電話会議** アドオン ライセンスを少なくとも 1 件購入する必要があります。

3. 割り当てられている電話番号を表示するには、[状態] 列 **を参照** してください。

4. ビューをフィルター処理するには、フィルター アイコンをクリックします。 [フィルター **] ウィンドウ** では、ドロップダウン リストを使用して、次の方法でビューをフィルター処理できます。

   - **設定した** 数値範囲。 最も小さい数値または最大の数値で検索できます。

   - 指定した数値で始まる数値。

   - 番号 **のアクティブ化の状態**。

   - 数値 **の種類**。

   - 電話の **状態。**

## <a name="to-see-all-of-the-phone-numbers-that-are-assigned-to-users"></a>ユーザーに割り当てられているすべての電話番号を表示するには

ユーザーを設定するときに、ユーザーに既に割り当てられている電話番号と、ユーザーに割り当て可能な電話番号の一覧を表示したい場合があります。
  
![管理センターを使用Teams ](media/teams-logo-30x30.png) **ロゴをMicrosoft Teamsアイコン**

1. 管理センター **にMicrosoft Teams移動します**。

2. In the left navigation, go to **Voice** > **Phone numbers**.

    > [!IMPORTANT]
    > Microsoft Teams 管理センターの左側のナビゲーションに [音声] オプションを表示するには、まず、少なくとも 1 つの **Enterprise E5** ライセンス、1 つの **電話システム** アドオン ライセンス、または 1 つの電話会議アドオン ライセンスを購入する必要があります。

3. 割り当てられている数値をすばやく並べ替え、割り当てられている番号を確認するには、[状態] 列見出 **しを** クリックします。 または、フィルター アイコンをクリックし、ビューをフィルター処理して、ユーザーに既に割り当てられている電話番号、またはユーザーに割り当て可能な未割り当て番号を表示できます。 以下の分類でフィルターすることができます。

   - **ユーザーに割り当て済み**

   - **会議ブリッジに割り当て済み** 

   - **未割り当て**

## <a name="to-see-the-phone-numbers-that-are-assigned-to-voice-users"></a>音声ユーザーに割り当てられているすべての電話番号を表示するには

組織内のユーザーに電話の送受信を設定する場合は、まず電話番号を取得してから、ユーザーに割り当てる必要があります。 電話番号を取得した後は、番号の割り当てのアクティブ化の状態を確認したい場合があります。

![[管理センターを使用Teams ](media/teams-logo-30x30.png) **ロゴを示Microsoft Teamsアイコン**!
  
1. 管理センター **にMicrosoft Teams移動します**。

2. In the left navigation, go to **Voice** > **Phone numbers**.

    > [!IMPORTANT]
    > Microsoft Teams 管理センターの左側のナビゲーションに [音声] オプションを表示するには、まず、少なくとも 1 つの **Enterprise E5** ライセンス、1 つの **電話システム** アドオン ライセンス、または 1 つの電話会議アドオン ライセンスを購入する必要があります。

3. [フィルター] アイコンをクリックして、アクティブ化状態でビュー **をフィルター処理できます** 。次の方法でフィルター処理できます。

   - **アクティブ化**

   - **割り当て保留中**

   - **割り当てに失敗しました**

   - **更新プログラムの保留中**

   - **更新に失敗しました**

## <a name="using-the-teams-powershell-module"></a>PowerShell モジュールTeams使用する

Teams PowerShell モジュールを使用して前のセクションから同じ情報を取得できますが、バージョン 1.1.6 以降 (Skype for Business Online コネクタの統合を含む) が必要です。 モジュールの詳細については、PowerShell の概要に関[するMicrosoft Teamsを参照してください](teams-powershell-overview.md)。

[Get-CsOnlineTelephoneNumber](/powershell/module/skype/get-csonlinetelephonenumber)コマンドレットを使用して、組織のすべての電話番号の一覧を表示できます。 たとえば、次のコマンドを実行して、各電話番号とその状態を確認できます。

```PowerShell
Get-CsOnlineTelephoneNumber | ft Id,ActivationState
```

[Get-CsOnlineUser](/powershell/module/skype/get-csonlineuser)コマンドレットを使用すると、ユーザーに割り当てられているすべての電話番号を確認できます。 たとえば、次のコマンドを実行して、電話番号が割り当てられているすべてのユーザーを表示できます。

```PowerShell
Get-CsOnlineUser | Where-Object  { $_.LineURI -notlike $null } | ft DisplayName,UserPrincipalName,LineURI
```

## <a name="related-topics"></a>関連トピック
[電話番号の移行に関するよくある質問](./phone-number-calling-plans/port-order-overview.md)

[通話プランで使用されるさまざまな種類の電話番号](./different-kinds-of-phone-numbers-used-for-calling-plans.md)

[組織の電話番号を管理する](/microsoftteams/manage-phone-numbers-for-your-organization)

[緊急通話の利用条件](./emergency-calling-terms-and-conditions.md)

[緊急通話の免責事項ラベル](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

[Get-CsOnlineTelephoneNumber](/powershell/module/skype/get-csonlinetelephonenumber)
  
[Get-CsOnlineUser](/powershell/module/skype/get-csonlineuser)