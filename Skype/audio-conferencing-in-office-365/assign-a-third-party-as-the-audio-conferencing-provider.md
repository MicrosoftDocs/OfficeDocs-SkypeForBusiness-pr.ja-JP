---
title: "サードパーティを電話会議プロバイダーとして割り当てる"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: 77f68ca7-c1cf-40d9-9c23-87a6b2abe9de
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business, Microsoft Teams
localization_priority: Normal
ROBOTS: None
f1keywords:
- ms.lync.lac.DialInExportImport
- ms.lync.lac.DialInProvider
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
description: 'Learn how to set up a third-party as your dial-in conferencing provider with Skype for Business. '
ms.openlocfilehash: a53a2e63f15aa40eb6a88ab13daba2022b35e3b6
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/15/2017
---
# <a name="assign-a-third-party-as-the-audio-conferencing-provider"></a>サードパーティを電話会議プロバイダーとして割り当てる

オーディオ会議プロバイダーでは、*テレビ会議サービス*を提供します。 会議ブリッジでは、ダイヤルインの電話番号、Pin、および作成された会議の会議 Id を提供します。 ビジネスまたはマイクロソフトのチームの会議のスケジュールを設定したり Skype しようとする人に、オーディオ会議プロバイダーを割り当てる必要があるだけです。
  
> [!NOTE]
> Microsoft Teams の場合、ユーザーはサードパーティーの電話会議プロバイダーを使用できません。電話会議プロバイダーが Microsoft に設定される Office 365 の電話会議を使用する必要があります。 
  
## <a name="steps-to-do-before-you-can-assign-a-third-party-audio-conferencing-provider"></a>サードパーティーの電話会議プロバイダーを割り当てる前に実行する手順

1. Office 365 のプランによって、ユーザーが組織内に電話会議を使用するビジネスまたはマイクロソフトのチームの会議のスケジュールを設定したり Skype の**電話会議**のアドオンのライセンスを購入する必要があります。 詳細については、 [Skype](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)を参照してください。
    
2. **オーディオ会議**のアドオンのライセンスを購入した場合は、オーディオ会議を使用する会議やスケジュールを設定する、組織内のユーザーに割り当てます。 [ビジネスおよびマイクロソフトのチームのライセンスを Skype を割り当てる](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)を参照してください。
    
    > [!NOTE]
    > **電話会議**ライセンスをサードパーティーの電話会議プロバイダーに割り当てた **後に** 、任意のユーザーに割り当てる場合、そのユーザーは自動的に Microsoft を電話会議プロバイダーとして使用するように設定されます。このような場合は、サードパーティーの電話会議プロバイダーを割り当てる前に、Microsoft を電話会議プロバイダーとして削除する必要があります。
  
3. サードパーティーの電話会議プロバイダーは、[Microsoft PinPoint](https://go.microsoft.com/fwlink/?LinkId=797530) で見つけてください。セットアップ方法については、これらのプロバイダーに連絡して確認してください。
    
    サードパーティーのダイヤルイン会議プロバイダーから以下の情報が提供されます。
    
  - **ダイヤルイン番号 (有料)** とフリーダイヤルの番号 (提供されている場合)。
    
  - **会議 Id。これは会議をスケジュールする各ユーザーが使用します。一部の** 。これは会議をスケジュールする各ユーザーで使用されます。一部の ACP では、これらのパスコードが要求されます。
    
    > [!NOTE]
    > サードパーティー ACP の初回のセットアップを完了したが変更する必要が生じた場合には、[ **Microsoft Bridge**] ページの下部で **ここをクリックしてサードパーティーの音声会議プロバイダーを構成してください**。 
  
    > [!NOTE]
    > ある人を電話会議に対して有効にして、サードパーティーの電話会議プロバイダーを割り当てると、音声会議と会議の ID (パスコード) が、これらにより作成される **新しい** Skype for Business Online会議に自動的に追加されます。
  
## <a name="how-to-assign-a-third-party-audio-conferencing-provider-to-a-user"></a>サードパーティー電話会議プロバイダーをユーザーに割り当てる方法

1. [ **Skype for Business 管理センター**] で、[ **ユーザー**] を選択します。リストからユーザーを選び、操作ウィンドウで [ **編集**] をクリックします。
    
2. ユーザーのプロパティ ページで [ **電話会議**] をクリックして次の情報を入力します。
    
  - **プロバイダー名**サードパーティのプロバイダーを一覧から選択します。
    
  - [ **既定の有料電話番号**] これは必須です。
    
  - [ **既定のフリー ダイヤル番号**] これは必須です。
    
  - [ **会議 ID**] ご利用の音声会議プロバイダーから提供されます。
    
3. [ **保存**] をクリックします。
    
4. 各ユーザーに電話会議プロバイダーから受け取った PIN を送信します。この PIN は電話会議の開催者またはリーダーとしてコールインするために必要です。
    
    > [!NOTE]
    > サードパーティーの電話会議プロバイダーを使用している場合、会議の開催者の代わりに PIN を表示 / 設定する方法はありません。 
  
## <a name="how-to-assign-a-third-party-audio-conferencing-provider-to-many-people-at-the-same-time"></a>サードパーティーの電話会議プロバイダーを多数の人に同時に割り当てる方法

1. **ビジネス管理センターの Skype**では、**オーディオ会議**を選択します。 > **マイクロソフトのブリッジ**です。 ページの下部には、**代わりに、サード ・ パーティ製のオーディオ会議プロバイダーを構成するにはここをクリックして**リンクをクリックします。
    
    > [!NOTE]
    > 行う場合、サード パーティ製の ACP の最初のセットアップが、今すぐ**ここをクリックすると、サード ・ パーティ製のオーディオ会議プロバイダーを構成するのには**、**マイクロソフトのブリッジ**のページの下部にある変更を行う必要があります。 
  
2. [ **サードパーティーの音声会議プロバイダーを構成する**] ページで、[ **ユーザーのインポートおよびエクスポート**] の [ **エクスポート ウィザード**] をクリックして [ **ユーザーのエクスポート ウィザード**] の手順を実行します。完了すると、電話会議に設定する人を一覧表示するファイルを入手します。
    
3. 作成したファイルをサードパーティーの電話会議プロバイダーに送信します。プロバイダーはファイルに一覧表示された人の電話会議情報を追加して、ファイルを返送します。
    
4. 返送されたファイルに正しい情報が含まれていることを慎重に確認してください。ファイルに一覧表示された人が正しい情報を取得していない場合があることがわかっています。
    
5. [ **サードパーティーの音声会議プロバイダーを構成する**] で、[ **ユーザーのインポートおよびエクスポート**] の [ **インポート ウィザード**] をクリックして、[ **ユーザーのインポート ウィザード**] の手順を実行します。
    
6. 各ユーザーに電話会議プロバイダーから受け取った PIN を送信します。この PIN は電話会議の開催者またはリーダーとしてコールインするために必要です。
    
    > [!NOTE]
    > サードパーティーの電話会議プロバイダーを使用している場合、会議の開催者の代わりに PIN を表示 / 設定する方法はありません。 
  
## <a name="when-to-use-a-third-party-audio-conferencing-provider"></a>サードパーティーの電話会議プロバイダーを使用する場合

Office 365 の電話会議を利用できない国または地域にお住まいの場合は、場所が原因でサービス品質が低下します。サードパーティーの電話会議プロバイダーとの既存の契約がある場合は、サードパーティーの電話会議プロバイダーを使用することをお勧めしますが、それ以外の場合は、マイクロソフトを電話会議プロバイダーとして使用してください。
  
## <a name="automate-assigning-the-third-party-audio-conferencing-provider-by-using-windows-powershell"></a>Windows PowerShell を使用して、サードパーティーの音声会議プロバイダーとしての割り当てを自動化する

- 時間を節約したり、自動化したりするために、[Set-CsUserAcp](https://go.microsoft.com/fwlink/?LinkId=716851) コマンドレットを使用できます。
    
    > [!NOTE]
    > プロバイダーを Microsoft からサードパーティーの電話会議プロバイダーに変更するには、Microsoft を電話会議プロバイダーから削除する必要があります。これを行うには、[Disable-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617692 ) コマンドレットを使用します。
  
- Windows PowerShell の使い方の詳細については、「[Windows PowerShell を使用した一般的な Skype for Business Online の管理タスクの実行](https://go.microsoft.com/fwlink/?LinkId=525038)」をご覧ください。
    
## <a name="what-else-do-i-need-to-know"></a>他に必要な情報について

組織内のユーザーは、オーディオ会議プロバイダーを 1 つのみを使用できます。 マイクロソフトに個人の電話会議プロバイダーを変更するには、[マイクロソフトのユーザーのオーディオ会議プロバイダーを移動](moving-a-user-s-audio-conferencing-provider-to-microsoft.md)または[オーディオ会議プロバイダーとしてのマイクロソフトの割り当て](assign-microsoft-as-the-audio-conferencing-provider.md)を参照してください。
  
## <a name="related-topics"></a>関連トピック

[Skype for Business および Microsoft Teams の電話会議のセットアップ](set-up-audio-conferencing.md)
  
[Skype for Business Online のセットアップ](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)
  

