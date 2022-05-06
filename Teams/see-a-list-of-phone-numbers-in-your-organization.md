---
title: 組織内の電話番号の一覧を表示する
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: davlick, roykuntz, jastark
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
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Calling Plans
- seo-marvel-mar2020
description: Microsoft Teams管理センターを使用して、組織内のすべての電話番号と、ユーザーに割り当てられている、または割り当てられていないすべての番号の一覧を表示する方法について説明します。
ms.openlocfilehash: 45d292ae1ba4ffd714f0c302fe140978968ba1c9
ms.sourcegitcommit: 2e8daa3511cd198b3e0d43b153dd37a59cb21692
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/11/2022
ms.locfileid: "62763630"
---
# <a name="see-a-list-of-telephone-numbers"></a>電話番号の一覧を表示する 

電話会議[や](deploy-audio-conferencing-teams-landing-page.md)[通話キュー](plan-auto-attendant-call-queue.md)などのユーザーや音声アプリケーションに割り当てることができる電話番号には、さまざまな種類があります。 詳細については、「 [組織の電話番号を管理する」を参照してください](/microsoftteams/manage-phone-numbers-landing-page)。

この記事は、通話プランとオペレーター接続に適用されます。 ダイレクト ルーティングの詳細については、「 [電話番号を構成してエンタープライズ音声を有効にする](direct-routing-enable-users.md#configure-the-phone-number-and-enable-enterprise-voice)」を参照してください。
  
## <a name="to-see-all-telephone-numbers-in-your-organization"></a>組織内のすべての電話番号を表示するには

組織内のすべての電話番号の一覧を表示するには:

1. **Microsoft Teams管理センター** に移動します。

2. In the left navigation, go to **Voice** > **Phone numbers**.

3. 割り当てられている電話番号を表示するには、割り当てられているサービスの種類も示されている **[割り当て状態]** 列を参照してください。

4. ビューをフィルター処理するには、フィルター アイコンをクリックします。 [ **フィルター** ] ウィンドウで、ドロップダウン リストを使用してビューをフィルター処理できます。

   - 設定した **数値範囲**。 最も小さい数値または最も高い数値で検索できます。

   - 指定した数値で始まる数値。

   - 番号 **アクティブ化の状態**。

   - 数値 **の種類**。

   - 電話番号 **の状態**。

## <a name="to-see-all-telephone-numbers-that-are-assigned-to-users"></a>ユーザーに割り当てられているすべての電話番号を表示するには

ユーザーを設定するときに、ユーザーに既に割り当てられている電話番号と、割り当て可能な電話番号の一覧を表示する必要がある場合があります。

1. **Microsoft Teams管理センター** に移動します。

2. In the left navigation, go to **Voice** > **Phone numbers**.

    > [!IMPORTANT]
    > Microsoft Teams管理センターの左側のナビゲーションで **[音声**] オプションを表示するには、最初に少なくとも 1 つの **Enterprise E5 ライセンス**、1 つの **電話システム** アドオン ライセンス、または 1 つの電話会議アドオン ライセンス **を購入する** 必要があります。

3. 割り当てられている数値をすばやく並べ替えるには、[割り当て **状態]** 列見出しをクリックします。 または、フィルター アイコンをクリックし、ビューをフィルター処理して、既にユーザーに割り当てられている電話番号またはユーザーに割り当てることができる割り当てられていない番号を表示することもできます。 以下の分類でフィルターすることができます。

   - **ユーザーに割り当てられている**
   - **会議ブリッジに割り当てられている** 
   - **音声アプリに割り当てられる (自動応答/通話キュー)**
   - **未割り当て**

## <a name="to-see-all-telephone-numbers-that-are-assigned-to-voice-users"></a>音声ユーザーに割り当てられているすべての電話番号を表示するには

組織内のユーザーが電話を発信および受信するように設定する場合は、最初に電話番号を取得してからユーザーに割り当てる必要があります。 電話番号を取得したら、番号の割り当てのアクティブ化状態を確認できます。
  
1. **Microsoft Teams管理センター** に移動します。

2. In the left navigation, go to **Voice** > **Phone numbers**.

3. フィルター アイコンをクリックして、 **アクティブ化状態** でビューをフィルター処理します。 以下の分類でフィルターすることができます。

   - **アクティブ**
   - **割り当て保留中**
   - **割り当てが失敗しました**
   - **保留中の更新プログラム**
   - **更新に失敗しました**

## <a name="using-the-teams-powershell-module"></a>Teams PowerShell モジュールの使用

Teams PowerShell モジュールを使用すると、前のセクションと同じ情報を取得できますが、バージョン 1.1.6 以降 (Skype for Business Online コネクタの統合を含む) が必要です。 モジュールの詳細については、[PowerShell の概要Microsoft Teams](teams-powershell-overview.md)参照してください。

組織のすべての電話番号の一覧を表示するには、 [Get-CsOnlineTelephoneNumber](/powershell/module/skype/get-csonlinetelephonenumber) コマンドレットを使用します。 たとえば、各電話番号とその状態を確認するには、次のコマンドを実行します。

```PowerShell
Get-CsOnlineTelephoneNumber | ft Id,ActivationState
```

ユーザーに割り当てられているすべての電話番号を表示するには、 [Get-CsOnlineUser](/powershell/module/skype/get-csonlineuser) コマンドレットを使用します。 たとえば、電話番号が割り当てられているすべてのユーザーを表示するには、次のコマンドを実行します。

```PowerShell
Get-CsOnlineUser | Where-Object  { $_.LineURI -notlike $null } | ft DisplayName,UserPrincipalName,LineURI
```

## <a name="related-topics"></a>関連項目

[組織の電話番号を管理する](manage-phone-numbers-landing-page.md)

[緊急通話の利用条件](./emergency-calling-terms-and-conditions.md)

[緊急通話の免責事項ラベル](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

[Get-CsOnlineTelephoneNumber](/powershell/module/skype/get-csonlinetelephonenumber)
  
[Get-CsOnlineUser](/powershell/module/skype/get-csonlineuser)