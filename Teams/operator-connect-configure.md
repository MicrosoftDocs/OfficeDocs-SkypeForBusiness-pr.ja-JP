---
title: オペレーター の構成Connect
author: cazawideh
ms.author: czawideh
manager: serdars
ms.date: 09/30/2021
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
- m365initiative-voice
ms.reviewer: crowe
search.appverid: MET150
f1.keywords:
- NOCSH
- ms.teamsadmincenter.directrouting.overview
description: オペレーター アカウントを構成する方法の詳細についてはConnect。
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: aa31a954bb36369417f408734fa3b1622e101e69
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/05/2022
ms.locfileid: "62384165"
---
# <a name="configure-operator-connect"></a>オペレーター の構成Connect

この記事では、オペレーター アカウントを構成する方法についてConnect。 オペレーター サービスを構成するConnect前提条件とライセンスの詳細については、「オペレーター向けプラン [Connect」を](operator-connect-plan.md)参照してください。

## <a name="enable-an-operator"></a>演算子を有効にする

管理者センターでオペレーターを有効、編集、削除Teamsできます。 左側のナビゲーション ウィンドウで、[Voice > **Operators] に移動します**。

演算子を有効にするには:

1. **演算子を選択します。** [すべての演算子 **] タブで** 、リージョンまたはサービス別に使用可能な演算子をフィルター処理して、音声ニーズに合った適切な演算子を検索します。 次に、有効にする演算子を選択します。  

2. **国を選択します。** [ **オペレーター設定]** で、選択したオペレーターで有効にする国を選択します。

3. **連絡先情報を入力する** 氏名やメール アドレスなどの連絡先情報は、オペレーターと自動的に共有されます。 この情報は後で変更できます。 さらに、会社の規模を指定する必要があります。また、電話番号を指定することもできます。 オペレーターは、この情報を使用して、オペレーターサービスの詳細について連絡Connect。

4. データ転送に関する通知に同意します。

5. **演算子を追加します。** [ **Add as my operator]を選択して** 保存します。

## <a name="set-up-phone-numbers"></a>電話番号を設定する

電話番号の設定方法は、新しいユーザーの番号を設定するか、Microsoft 通話プランまたは直接ルーティングから既存の番号を移動するかによって異なります。

- 新しいユーザーの電話番号を取得する必要がある場合は、「新しいユーザーの電話番号を取得する[」をTeamsしてください](#acquire-numbers-for-new-teams-users)。

- 通話プランからオペレーター グループに既存の番号を移動する場合は、「通話プランからオペレーターグループに番号を移動Connect」[を参照Connect](#move-numbers-from-calling-plans-to-operator-connect)。

- 既存の番号を直接ルーティングからオペレーター グループに移動する場合Connect、直接ルーティングからオペレーターへの番号の移動に関する[ページConnect](#move-numbers-from-direct-routing-to-operator-connect)。

### <a name="acquire-numbers-for-new-teams-users"></a>新しいユーザーの数値をTeamsする

新しいユーザーの番号を取得するにはTeams次の手順に従います。

1. **ライセンスを割り電話システムします。** ユーザーにライセンス ライセンス電話システム割り当てるには、Microsoft 365 管理センター PowerShell を使用します。 詳細については、「アドオン ライセンスを[ユーザーにTeams割り当てる」を参照してください](teams-add-on-licensing/assign-teams-add-on-licenses.md)。

2. オペレーター アカウントで取得した電話番号が割り当てられるConnect TeamsOnly モードである必要があります。 組織が TeamsOnly モードの場合、すべてのユーザーが TeamsOnly モードになります。 これを確認するには、管理センター Teams、アップグレード設定のTeams > Teams **移動します**。 組織が諸島モードの場合は、特定のユーザーが TeamsOnly モードを使用している必要があります。 [ユーザー] **に移動** し、ユーザー アカウントを選択します。 [**アカウント]** タブの [アップグレード **Teams、** 共存モードを 'TeamsOnly' に設定する必要があります。

3. **数値を取得します。** オペレーターの Web サイトに移動して、電話番号を注文して取得します。 オペレーター Web サイトの一覧については、オペレーターの web サイトMicrosoft 365[覧Connectしてください](https://cloudpartners.transform.microsoft.com/practices/microsoft-365-for-operators/directory)。 テナント ID を指定する必要があります。 テナント ID が分からない場合は、「テナント ID を確認する[」Microsoft 365を](/onedrive/find-your-office-365-tenant-id)参照してください。

4. **数値を割り当てる。** オペレーターが注文を完了すると、テナントに番号がアップロードされます。 [Voice > 電話 numbers] に移動すると、Teams管理センターで **番号とプロバイダー> 電話できます**。 管理者センターまたは PowerShell を使用して、Teamsユーザーに番号を割り当てる。 詳細については、「数値を割り当てる [」を参照してください](#assign-numbers)。

> [!NOTE]
> ユーザー [の電話番号を](getting-phone-numbers-for-your-users.md)取得する以外に、電話会議 (電話会議ブリッジ)、自動応答、通話キュー (サービス番号とも呼ばれる) などのサービスの有料電話番号または無料電話番号を取得できます。 サービス用電話番号の同時通話容量は、ユーザーまたは登録者の電話番号より大きくなります。 たとえば、サービス番号は何百もの呼び出しを同時に処理できるのに対し、ユーザーの電話番号は数件の通話のみを同時に処理できます。 サービス番号を取得するには、オペレーターにお問い合わせください。

### <a name="emergency-addresses"></a>緊急対応の住所

緊急対応の住所は、番号に関連付けられている静的な場所です。 Teams 管理センターで緊急対応の住所を作成すると、住所の割り当て方法や後で変更する方法はオペレーターによって異なっています。

緊急対応の住所に番号を割り当てるには、オペレーターが次の 3 つのシナリオのいずれかを実装します。

- オペレーターは電話番号に緊急対応の住所を割り当て、後で管理センターで変更Teamsできます。

- オペレーターは住所を割り当てないので、管理センターの電話番号に緊急対応の住所Teamsできます。

- オペレーターは緊急対応の住所を電話番号に割り当て、変更を許可しません。 このシナリオでは、電話番号と割り当てられた緊急対応の住所を変更するために、オペレーターに連絡する必要があります。

緊急通話の詳細については、「緊急通話の管理 [」と「](what-are-emergency-locations-addresses-and-call-routing.md) 動的緊急通話の計画と構成 [」を参照してください](configure-dynamic-emergency-calling.md)。

### <a name="move-numbers-from-calling-plans-to-operator-connect"></a>通話プランからオペレーター プランに番号を移動Connect

1. オペレーターに問い合わせ、番号をオペレーターに移植Connect。 オペレーター[の web Microsoft 365については、「Connect Operator Connect ディレクトリ](https://cloudpartners.transform.microsoft.com/practices/microsoft-365-for-operators/directory)」を参照してください。

2. オペレーターが移植注文を完了したら、ユーザーの通話プランの電話番号の割り当てを解除し、通話プラン ライセンスを削除できます。 その後、オペレーターはテナントに番号をアップロードできます。

3. 管理者センター Connect PowerShell を使用して、オペレーターにTeams番号を割り当てる。 詳細については、「数値を割り当てる [」を参照してください](#assign-numbers)。

### <a name="move-numbers-from-direct-routing-to-operator-connect"></a>直接ルーティングからオペレーター グループに番号を移動Connect

番号を直接ルーティングからオペレーター Connect に移動するには、オペレーターによってテナントにアップロードされた既存の直接ルーティング番号を、割り当てられているユーザーから削除する必要があります。 その後、番号がオペレーター アカウントに移行Connect、その番号をユーザーに再割り当てできます。 オンプレミスまたはオンラインの電話番号を使用Connect直接ルーティングからオペレーター への移行を行う場合は、次の手順に従います。

>[!IMPORTANT]
> 電話番号は移行中にサービスが利用しないので、開始する前にオペレーターとConnect調整してください。

#### <a name="step-1---remove-existing-direct-routing-numbers"></a>手順 1 - 既存の直接ルーティング番号を削除します。

既存の直接ルーティング番号を削除する方法は、番号がオンプレミスかオンラインかによって異なります。 確認するには、次のコマンドを実行します。
    
```PowerShell
Get-CsOnlineUser -Identity <user> | fl RegistrarPool,OnPreLineURIManuallySet, OnPremLineURI, LineURI 
```

が `OnPremLineUriManuallySet` に設定`False``LineUri`され、E.164 電話番号が設定されている場合、電話番号はオンプレミスに割り当て済みであり、Office 365。
    
**オンプレミスに割り当てられている直接ルーティング番号を削除するには、次の** コマンドを実行します。
    
```PowerShell
Set-CsUser -Identity <user> -LineURI $null 
```

削除が有効にするのにかかる時間は、構成によって異なります。 オンプレミスの番号が削除され、変更が同期されたのを確認するには、次の PowerShell コマンドを実行します。 
    
```PowerShell
Get-CsOnlineUser -Identity <user> | fl RegistrarPool,OnPreLineURIManuallySet, OnPremLineURI, LineURI 
```
       
変更がオンライン ディレクトリに同期Office 365、期待される出力は次の通りです。 
       
 ```console
RegistrarPool                        : pool.infra.lync.com
 OnPremLineURIManuallySet             : True
 OnPremLineURI                        : 
LineURI                              : 
```

<br> **オンラインで割り当てる既存のオンラインダイレクト ルーティング番号を削除するには、次の** PowerShell コマンドを実行します。


```PowerShell
Remove-CsPhoneNumberAssignment -Identity <user> -PhoneNumber <pn> -PhoneNumberType DirectRouting
```

電話番号を削除すると、最大 10 分かかる場合があります。 まれに、最大 24 時間かかる場合があります。 オンプレミスの番号が削除され、変更が同期されたのを確認するには、次の PowerShell コマンドを実行します。 


```PowerShell
Get-CsOnlineUser -Identity <user> | fl Number
```

#### <a name="step-2---remove-the-online-voice-routing-policy-associated-with-your-user"></a>手順 2 - ユーザーに関連付けられているオンライン音声ルーティング ポリシーを削除する

番号が割り当てられていない場合は、次の PowerShell コマンドを実行して、ユーザーに関連付けられているオンライン音声ルーティング ポリシーを削除します。

```PowerShell
Grant-CsOnlineVoiceRoutingPolicy -Identity <user> -PolicyName $Null
```

#### <a name="step-3---acquire-phone-numbers"></a>手順 3 - 電話番号を取得する

オペレーターの Web サイトに移動して、電話番号を注文して取得します。 演算子の Web サイトを見つけるには、演算子のMicrosoft 365[を参照Connectしてください](https://cloudpartners.transform.microsoft.com/practices/microsoft-365-for-operators/directory)。 テナント ID を指定する必要があります。 テナント ID が分からない場合は、「テナント ID を確認する[」Microsoft 365を](/onedrive/find-your-office-365-tenant-id)参照してください。

#### <a name="step-4---assign-phone-numbers"></a>手順 4 - 電話番号を割り当てる

オペレーターが注文を完了すると、テナントに番号がアップロードされます。 [Voice > 電話 numbers] に移動すると、Teams管理センターで **番号とプロバイダー> 電話できます**。 管理者センター Connect PowerShell を使用して、オペレーターにTeams番号を割り当てる。 詳細については、「数値を割り当てる [」を参照してください](#assign-numbers)。

### <a name="assign-numbers"></a>数値を割り当てる

ユーザーに電話番号を割り当てる方法については、「ユーザーの電話番号を割り当て、変更、または削除 [する」を参照してください](assign-change-or-remove-a-phone-number-for-a-user.md)。

## <a name="manage-your-operators"></a>オペレーターを管理する

[演算子 **] タブ** から、演算子とその状態を表示し、選択内容に次の変更を加えます。  

- 国別にオペレーター サービスを管理する
- 演算子を中断する
- 演算子を削除する

> [!NOTE]
> 組織または国からオペレーターを削除する前に、組織または国のユーザーに割り当てられているすべての電話番号を削除し、オペレーターに連絡して番号を解放する必要があります。

## <a name="release-numbers"></a>リリース番号

管理センターから電話番号を解放Teams、[電話番号] ページに移動電話番号を選択します。

- 電話番号がユーザーに割り当てられていない場合は、[リリース] を選択 **します**。

- 電話番号がユーザーに割り当てられている場合は、番号の割り当てを解除する必要があります。 [編集 **] を選択** し、[ユーザーの **削除] を選択します**。 変更を保存した後、[リリース] を **選択します**。

## <a name="related-topics"></a>関連項目

- [自動応答Teamsキューの計画](plan-auto-attendant-call-queue.md)
