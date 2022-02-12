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
description: Microsoft Teams 管理センターを使用して、組織内のすべての電話番号と、ユーザーに割り当てられている、または割り当てられていないすべての電話番号の一覧を表示する方法について学習します。
ms.openlocfilehash: 45d292ae1ba4ffd714f0c302fe140978968ba1c9
ms.sourcegitcommit: 2e8daa3511cd198b3e0d43b153dd37a59cb21692
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/11/2022
ms.locfileid: "62763630"
---
# <a name="see-a-list-of-telephone-numbers"></a>電話番号の一覧を表示する 

電話会議や通話キューなど、ユーザーや音声アプリケーションに割り当て可能な電話番号には、[さまざまな](deploy-audio-conferencing-teams-landing-page.md)[種類があります](plan-auto-attendant-call-queue.md)。 詳細については、「組織の電話番号 [を管理する」を参照してください](/microsoftteams/manage-phone-numbers-landing-page)。

この記事は、通話プランとオペレーター サービスにConnect。 ダイレクト ルーティングの詳細については、「電話番号を構成し、エンタープライズ音声を有効 [にする」を参照してください](direct-routing-enable-users.md#configure-the-phone-number-and-enable-enterprise-voice)。
  
## <a name="to-see-all-telephone-numbers-in-your-organization"></a>組織内のすべての電話番号を表示するには

組織内のすべての電話番号の一覧を表示するには:

1. 管理センター **のMicrosoft Teams移動します**。

2. In the left navigation, go to **Voice** > **Phone numbers**.

3. 割り当てられている電話番号を表示するには、[割り当ての状態] 列を参照してください。この列には、番号が割り当てられているサービスの種類も表示されます。

4. ビューをフィルター処理するには、フィルター アイコンをクリックします。 [フィルター **] ウィンドウ** では、ドロップダウン リストを使用して、次の方法でビューをフィルター処理できます。

   - **設定した** 数値範囲。 最も小さい数値または最大の数値で検索できます。

   - 指定した数値で始まる数値。

   - 番号 **のアクティブ化状態**。

   - 数値 **の種類**。

   - 電話状態を **確認します**。

## <a name="to-see-all-telephone-numbers-that-are-assigned-to-users"></a>ユーザーに割り当てられているすべての電話番号を表示するには

ユーザーを設定するときに、ユーザーに既に割り当てられている電話番号と、ユーザーに割り当て可能な電話番号の一覧を表示したい場合があります。

1. 管理センター **のMicrosoft Teams移動します**。

2. In the left navigation, go to **Voice** > **Phone numbers**.

    > [!IMPORTANT]
    > Microsoft Teams 管理センターの左側のナビゲーションに [音声] オプションを表示するには、まず、少なくとも 1 つの **Enterprise E5** ライセンス、1 つの **電話システム** アドオン ライセンス、または 1 つの電話会議アドオン ライセンスを購入する必要があります。

3. 割り当てられている番号をすばやく並べ替え、割り当てられている番号を確認するには、[割り当て状態] 列見出 **しを** クリックします。 または、フィルター アイコンをクリックし、ビューをフィルター処理して、ユーザーに既に割り当てられている電話番号、またはユーザーに割り当て可能な未割り当て番号を表示できます。 以下の分類でフィルターすることができます。

   - **ユーザーに割り当て済み**
   - **会議ブリッジに割り当て済み** 
   - **Voice アプリに割り当て済み (自動応答/通話キュー)**
   - **未割り当て**

## <a name="to-see-all-telephone-numbers-that-are-assigned-to-voice-users"></a>音声ユーザーに割り当てられているすべての電話番号を表示するには

組織内のユーザーに電話の送受信を設定する場合は、まず電話番号を取得してから、ユーザーに割り当てる必要があります。 電話番号を取得した後は、番号の割り当てのアクティブ化の状態を確認できます。
  
1. 管理センター **のMicrosoft Teams移動します**。

2. In the left navigation, go to **Voice** > **Phone numbers**.

3. フィルター アイコンをクリックして、アクティブ化状態でビュー **をフィルター処理します**。 以下の分類でフィルターすることができます。

   - **アクティブ化**
   - **割り当て保留中**
   - **割り当てに失敗しました**
   - **更新プログラムの保留中**
   - **更新に失敗しました**

## <a name="using-the-teams-powershell-module"></a>PowerShell モジュールTeams使用する

Teams PowerShell モジュールを使用して前のセクションから同じ情報を取得できますが、バージョン 1.1.6 以降 (Skype for Business Online コネクタの統合を含む) が必要です。 モジュールの詳細については、「[PowerShell の概要Microsoft Teams参照してください](teams-powershell-overview.md)。

組織のすべての電話番号の一覧を表示するには、 [Get-CsOnlineTelephoneNumber コマンドレットを使用](/powershell/module/skype/get-csonlinetelephonenumber) します。 たとえば、各電話番号とその状態を表示するには、次のコマンドを実行します。

```PowerShell
Get-CsOnlineTelephoneNumber | ft Id,ActivationState
```

ユーザーに割り当てられているすべての電話番号を表示するには、 [Get-CsOnlineUser コマンドレットを使用](/powershell/module/skype/get-csonlineuser) します。 たとえば、電話番号が割り当てられているすべてのユーザーを表示するには、次のコマンドを実行します。

```PowerShell
Get-CsOnlineUser | Where-Object  { $_.LineURI -notlike $null } | ft DisplayName,UserPrincipalName,LineURI
```

## <a name="related-topics"></a>関連項目

[組織の電話番号を管理する](manage-phone-numbers-landing-page.md)

[緊急通話の利用条件](./emergency-calling-terms-and-conditions.md)

[緊急通話の免責事項ラベル](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

[Get-CsOnlineTelephoneNumber](/powershell/module/skype/get-csonlinetelephonenumber)
  
[Get-CsOnlineUser](/powershell/module/skype/get-csonlineuser)