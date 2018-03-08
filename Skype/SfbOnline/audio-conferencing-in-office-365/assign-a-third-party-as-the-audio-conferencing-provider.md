---
title: "電話会議プロバイダーとしてサードパーティを割り当てる"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 77f68ca7-c1cf-40d9-9c23-87a6b2abe9de
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords:
- ms.lync.lac.DialInExportImport
- ms.lync.lac.DialInProvider
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
description: "Skype for Business とのダイヤルイン会議プロバイダーとしてサードパーティを設定する方法について説明します。 "
ms.openlocfilehash: 5ae513c754764933f08370139eeb557f0fb39211
ms.sourcegitcommit: 2d84f687ccc44220d5ec9d8b429dfae65cced5a7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/01/2018
---
# <a name="assign-a-third-party-as-the-audio-conferencing-provider"></a>電話会議プロバイダーとしてサードパーティを割り当てる

電話会議プロバイダーは*会議ブリッジ*を提供します。会議ブリッジにダイヤルイン電話番号、ピン、作成した会議の会議 Id を提供します。Skype を潜在顧客のビジネスまたは Microsoft チーム会議やスケジュールを設定する人に電話会議プロバイダーを割り当てる必要があるだけです。
  
> [!NOTE]
> Microsoft チームのユーザーがサードパーティ電話会議プロバイダーを使用できません、Office 365 で、電話会議プロバイダーを Microsoft に設定している電話会議を使用する必要があります。 
  
## <a name="steps-to-do-before-you-can-assign-a-third-party-audio-conferencing-provider"></a>サードパーティ電話会議プロバイダーを割り当てることができる前に実行する手順を実行します。

1. によっては、Office 365 プランでは、スケジュールされたり、Skype for Business または Microsoft チーム会議の音声会議を使用する組織内のユーザーの**電話会議**アドオン ライセンスを購入する必要があります。詳細については、 [Skype for Business や Microsoft チーム アドオンのライセンス](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)を参照してください。
    
2. **電話会議**アドオン ライセンスを購入した場合は、スケジュールの設定、または電話会議を使用する会議を進行するユーザーは、組織のユーザーに割り当てます。[ビジネスや Microsoft チームのライセンスを割り当てる Skype](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)を参照してください。
    
    > [!NOTE]
    > **後**サードパーティ電話会議プロバイダーを割り当てるユーザーに**電話会議**のライセンスを割り当てる場合、代わりに、電話会議プロバイダーとして Microsoft を使用するユーザーが自動的に設定されます。このような場合は、サードパーティ電話会議プロバイダーにそれらを割り当てるには前に、電話会議プロバイダーとして Microsoft を最初に削除する必要があります。
  
3. [Microsoft PinPoint](https://go.microsoft.com/fwlink/?LinkId=797530)では、サードパーティ電話会議プロバイダーを検索します。連絡を取るし、それらのファイルを設定する項目を取得する方法について説明します。
    
    されます。
    
  - **ダイヤルイン番号 (有料)**と利用可能な場合はフリー ダイヤルの番号。
    
  - 会議をスケジュールするユーザーごとの使用されている**会議 Id** 。一部の Acp では、これらの会議パスコードを呼び出します。
    
    > [!NOTE]
    > 場合は、サードパーティ ACP 用を設定する最初のようになりましたする必要しますが、あります**ここをクリックすると、サードパーティ電話会議プロバイダーを構成する** **Microsoft ブリッジ**ページの下部にある、変更を行います。 
  
    > [!NOTE]
    > 音声会議に人を有効にし、サードパーティ電話会議プロバイダーを割り当てると、会議 Id (パスコード) と音声番号は、**新しい**Skype for Business Online の会議を作成するに自動的に追加します。
  
## <a name="how-to-assign-a-third-party-audio-conferencing-provider-to-a-user"></a>サードパーティ電話会議プロバイダーをユーザーに割り当てる方法

1. **Skype for Business 管理センター**で、[**ユーザー**] を選びます。リストからユーザーを選択し、操作ウィンドウで [**編集**] をクリックします。
    
2. ユーザーのプロパティ] ページは、**電話会議**をクリックし、この情報を入力します。
    
  - **プロバイダー名**リストからサードパーティ プロバイダーを選択します。
    
  - **既定の電話番号**これが必要です。
    
  - **既定のフリー ダイヤル番号**これは必要ありません。
    
  - **電話会議 ID**これは、電話会議プロバイダーによって提供されます。
    
3. {[**保存**] をクリックします。}
    
4. 電話会議プロバイダーから受け取った暗証番号 (pin) を各ユーザーに送信します。PIN は、電話会議の開催者またはリーダーとしてコールインする必要があります。
    
    > [!NOTE]
    > サードパーティ電話会議プロバイダーを使っているときに参照するか、会議の開催者の代わりに Pin を設定する方法はありません。 
  
## <a name="how-to-assign-a-third-party-audio-conferencing-provider-to-many-people-at-the-same-time"></a>サードパーティ電話会議プロバイダーを多数のユーザーに同時に割り当てる方法

1. **Skype for Business 管理センター**で、[**音声会議**] を選びます > **Microsoft ブリッジ**します。ページの下部にあるには、**代わりに、サードパーティ電話会議プロバイダーを構成したい場合は、ここをクリックして**リンクをクリックします。
    
    > [!NOTE]
    > 場合は、サードパーティ ACP 用を設定する最初のようになりましたする必要しますが、あります**ここをクリックすると、サードパーティ電話会議プロバイダーを構成するのには**、 **Microsoft ブリッジ**ページの下部にある、変更を行います。 
  
2. **電話会議プロバイダーをサードパーティの構成**] ページの [**インポートとエクスポートのユーザー**] の下で、**エクスポート ウィザード**] をクリックし、[**ユーザーのエクスポート ウィザード**の手順に従います。完了したら、電話会議を設定する人の一覧が表示されているファイルがあります。
    
3. サードパーティ電話会議プロバイダーを作成したファイルを送信します。ファイルに記載されているユーザーの電話会議の情報を追加に戻って、ファイル、されます。
    
4. 返されたファイルが含まれている正しい情報にはことを確認してください。適切な情報を持っていないファイルに記載されているすべてのインスタンスのことができます。
    
5. **サードパーティ電話会議プロバイダーのページの構成**] の [**インポートとエクスポートのユーザー**の場合は、[**インポート ウィザード**] をクリックし、[**ユーザーのインポート ウィザード**の手順を実行
    
6. 電話会議プロバイダーから受け取った暗証番号 (pin) を各ユーザーに送信します。PIN は、電話会議の開催者、またはリーダーとしてコールインする必要があります。
    
    > [!NOTE]
    > サードパーティ電話会議プロバイダーを使っているときに参照するか、会議の開催者の代わりに Pin を設定する方法はありません。 
  
## <a name="when-to-use-a-third-party-audio-conferencing-provider"></a>サードパーティ電話会議プロバイダーを使用します。

サード パーティの音声を使用してをお勧めの国または地域を Office 365 で音声会議は使用できません、サービスの品質がない理由により、その場所では、とても便利なまたはサードパーティ電話会議プロバイダーを既存の契約がある場合は、会議のプロバイダーします。それ以外の場合、電話会議プロバイダーとしての Microsoft の使用をお勧めします。
  
## <a name="automate-assigning-the-third-party-audio-conferencing-provider-by-using-windows-powershell"></a>Windows PowerShell を使用して、サードパーティ電話会議プロバイダーを割り当てるを自動化します。

- 時間を節約し、自動化したりには、[セット CsUserAcp](https://go.microsoft.com/fwlink/?LinkId=716851)コマンドレットを使用することができます。
    
    > [!NOTE]
    > Microsoft からサードパーティ電話会議プロバイダーに、オーディオ プロバイダーを変更するには、電話会議プロバイダーとして Microsoft を削除する必要があります。これを行うには、[無効にする CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617692 )コマンドレットを使用します。
  
- 詳細については、Windows PowerShell を使用して、[共通の Skype for Business Online の管理タスクを実行する Windows PowerShell を使用する](https://go.microsoft.com/fwlink/?LinkId=525038)を参照してください。
    
## <a name="what-else-do-i-need-to-know"></a>他に必要な情報はありますか?

組織内のユーザーは、1 つの電話会議プロバイダーにのみ使用できます。Microsoft には、その人の電話会議プロバイダーを変更するには、 [Microsoft にユーザーの電話会議プロバイダーを移動](moving-a-user-s-audio-conferencing-provider-to-microsoft.md)または[電話会議プロバイダーとして Microsoft を割り当てる](assign-microsoft-as-the-audio-conferencing-provider.md)を参照してください。
  
## <a name="related-topics"></a>関連トピック

[Skype for Business とチームの Microsoft の音声会議をセットアップする設定します。](set-up-audio-conferencing.md)
  
[Skype for Business Online をセットアップします。](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)
  

