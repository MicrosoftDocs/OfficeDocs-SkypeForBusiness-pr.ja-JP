---
title: オペレーター接続を構成する
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
description: オペレーター接続を構成する方法の詳細について説明します。
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8d3b56a7935f31413829c89285fc81ee70023ab4
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/25/2022
ms.locfileid: "65675769"
---
# <a name="configure-operator-connect"></a>オペレーター接続を構成する

この記事では、オペレーター接続を構成する方法について説明します。 オペレーター接続を構成する前に、前提条件とライセンスの詳細については[、「オペレーター接続の計画](operator-connect-plan.md)」を参照してください。

## <a name="enable-an-operator"></a>演算子を有効にする

Teams管理センターで演算子を有効、編集、削除できます。 左側のナビゲーション ウィンドウで、[ **音声>演算子**] に移動します。

演算子を有効にするには:

1. **演算子を選択します。** [ **すべての演算子** ] タブで、使用可能な演算子をリージョンまたはサービス別にフィルター処理して、音声ニーズに適した演算子を見つけます。 次に、有効にする演算子を選択します。  

2. **国を選択します。** [ **オペレーターの設定**] で、選択した演算子で有効にする国を選択します。

3. **連絡先情報を入力する** 完全な名前と電子メール アドレスを含む連絡先情報は、オペレーターと自動的に共有されます。 この情報は後で変更できます。 さらに、会社の規模を指定する必要があり、電話番号を入力することもできます。 オペレーターはこの情報を使用して、オペレーター接続の詳細について連絡します。

4. データ転送に関する通知を受け入れます。

5. **演算子を追加します。** 保存 **する演算子として追加** を選択します。

## <a name="set-up-phone-numbers"></a>電話番号を設定する

電話番号の設定方法は、新しいユーザーの番号を設定するか、Microsoft 通話プランまたは直接ルーティングから既存の番号を移動するかによって異なります。

- 新しいユーザーの電話番号を取得する必要がある場合は、「[新しいTeams ユーザーの番号を取得する](#acquire-numbers-for-new-teams-users)」を参照してください。

- 既存の番号を通話プランからオペレーター接続に移動する場合は、「通話[プランからオペレーター接続に番号を移動する](#move-numbers-from-calling-plans-to-operator-connect)」を参照してください。

- 既存の番号を直接ルーティングからオペレーター接続に移動する場合は、「[直接ルーティングからオペレーター接続に番号を移動する](#move-numbers-from-direct-routing-to-operator-connect)」を参照してください。

### <a name="acquire-numbers-for-new-teams-users"></a>新しいTeams ユーザーの数値を取得する

新しいTeams ユーザーの番号を取得するには、次の手順に従います。

1. **電話システム ライセンスを割り当てます。** Microsoft 365 管理センターまたは PowerShell を使用して、電話システム ライセンスをユーザーに割り当てることができます。 詳細については、「[ユーザーにアドオン ライセンスTeams割り当てる」を参照してください](teams-add-on-licensing/assign-teams-add-on-licenses.md)。

2. オペレーター接続で取得した電話番号が割り当てられるユーザーは、TeamsOnly モードである必要があります。 組織が TeamsOnly モードの場合は、すべてのユーザーが TeamsOnly モードになります。 これを確認するには、Teams管理センターでTeams > Teams **アップグレード設定** に移動します。 組織がアイランド モードの場合は、特定のユーザーが TeamsOnly モードであるかどうかを確認します。 **[ユーザー]** に移動し、ユーザー アカウントを選択します。 [**アカウント**] タブの **[Teamsアップグレード**] で、共存モードを [TeamsOnly] に設定する必要があります。

3. **数値を取得します。** オペレーターの Web サイトに移動して、電話番号を注文して取得します。 オペレーター Web サイトの一覧については、[Microsoft 365 オペレーター接続 ディレクトリ](https://cloudpartners.transform.microsoft.com/practices/microsoft-365-for-operators/directory)に移動します。 テナント ID を指定する必要があります。 テナント ID がわからない場合は、「[Microsoft 365 テナント ID を検索](/onedrive/find-your-office-365-tenant-id)する」を参照してください。

4. **番号を割り当てます。** オペレーターが注文を完了すると、番号がテナントにアップロードされます。 ボイス > 電話番号に移動すると、Teams管理センターで番号とプロバイダー **を** 表示できます。 Teams管理センターまたは PowerShell を使用してユーザーに番号を割り当てます。 詳細については、「番号の [割り当て](#assign-numbers)」を参照してください。

> [!NOTE]
> [ユーザーの電話番号を取得](getting-phone-numbers-for-your-users.md)するだけでなく、電話会議 (会議ブリッジ)、自動応答、通話キュー (サービス番号とも呼ばれます) などのサービスの有料電話番号またはフリーダイヤル電話番号を取得できます。 サービス用電話番号の同時通話容量は、ユーザーまたは登録者の電話番号より大きくなります。 たとえば、サービス番号は数百の呼び出しを同時に処理できますが、ユーザーの電話番号は同時に少数の呼び出しのみを処理できます。 サービス番号を取得するには、オペレーターに問い合わせてください。

### <a name="emergency-addresses"></a>緊急対応のアドレス

緊急対応アドレスは、数値に関連付けられた静的な場所です。 Teams管理センターで緊急対応の住所を作成すると、住所の割り当て方法や後で変更する方法は、オペレーターによって異なります。

緊急時の住所に番号を割り当てるには、オペレーターは次の 3 つのシナリオのいずれかを実装します。

- オペレーターは電話番号に緊急対応の住所を割り当て、後でTeams管理センターで変更できます。

- オペレーターは住所を割り当てず、Teams管理センターの電話番号に緊急対応の住所を割り当てることができます。

- オペレーターは電話番号に緊急対応の住所を割り当て、それを変更することはできません。 このシナリオでは、電話番号と割り当てられた緊急対応の住所を変更するには、オペレーターに連絡する必要があります。

緊急通報の詳細については、「緊急通報の管理と動的 [緊急通報](what-are-emergency-locations-addresses-and-call-routing.md) の [計画と構成](configure-dynamic-emergency-calling.md)」を参照してください。

### <a name="move-numbers-from-calling-plans-to-operator-connect"></a>通話プランからオペレーター接続に番号を移動する

1. 電話番号をオペレーター接続に移植するには、オペレーターに問い合わせてください。 Microsoft 365 オペレーター接続[ディレクトリ](https://cloudpartners.transform.microsoft.com/practices/microsoft-365-for-operators/directory)を参照して、オペレーターの Web サイトを見つけます。

2. オペレーターが移植順序を完了したら、ユーザーの通話プランの電話番号の割り当てを解除し、通話プラン ライセンスを削除できます。 その後、オペレーターはテナントに番号をアップロードできます。

3. Teams管理センターを使用するか、PowerShell を使用してオペレーター接続番号をユーザーに割り当てます。 詳細については、「番号の [割り当て](#assign-numbers)」を参照してください。

### <a name="move-numbers-from-direct-routing-to-operator-connect"></a>ダイレクト ルーティングからオペレーター接続に番号を移動する

直接ルーティングからオペレーター接続に番号を移動するには、オペレーターによってテナントにアップロードされた既存のダイレクト ルーティング番号を、割り当てられているユーザーから削除する必要があります。 その後、番号をオペレーター接続に移行した後、ユーザーに番号を再割り当てることができます。 直接ルーティングから、オンプレミスまたはオンラインの電話番号を使用してオペレーター接続に移行するには、次の手順に従います。

>[!IMPORTANT]
> 移行中は電話番号が使用できなくなりますので、開始する前にオペレーター接続オペレーターと調整してください。

#### <a name="step-1---remove-existing-direct-routing-numbers"></a>手順 1 - 既存のダイレクト ルーティング番号を削除します。

既存のダイレクト ルーティング番号を削除する方法は、その番号がオンプレミスとオンラインのどちらに割り当てられているかによって異なります。 確認するには、次のTeams PowerShell モジュール コマンドを実行します。
    
```PowerShell
Get-CsOnlineUser -Identity <user> | fl RegistrarPool, OnPremLineURI, LineURI 
```

E.164 電話番号が入力されている場合`OnPremLineUri`、電話番号はオンプレミスに割り当てられ、Office 365に同期されました。
    
**オンプレミスに割り当てられているダイレクト ルーティング番号を削除するには、** 次のSkype for Business Server PowerShell コマンドを実行します。
    
```PowerShell
Set-CsUser -Identity <user> -LineURI $null 
```

削除が有効になるまでにかかる時間は、構成によって異なります。 オンプレミスの番号が削除され、変更が同期されているかどうかを確認するには、次のTeams PowerShell モジュール コマンドを実行します。 
    
```PowerShell
Get-CsOnlineUser -Identity <user> | fl RegistrarPool, OnPremLineURI, LineURI 
```
       
変更がオンライン ディレクトリOffice 365同期された後、予想される出力は次のようになります。 
       
 ```console
RegistrarPool                        : pool.infra.lync.com
OnPremLineURI                        : 
LineURI                              : 
```

<br> **オンラインで割り当てられている既存のオンライン ダイレクト ルーティング番号を削除するには、** 次のTeams PowerShell モジュール コマンドを実行します。


```PowerShell
Remove-CsPhoneNumberAssignment -Identity <user> -PhoneNumber <pn> -PhoneNumberType DirectRouting
```

電話番号を削除するには、最大で 10 分かかる場合があります。 まれに、最大 24 時間かかる場合があります。 電話番号が削除されたかどうかを確認するには、次のTeams PowerShell モジュール コマンドを実行します。 


```PowerShell
Get-CsOnlineUser -Identity <user> | fl LineUri
```

#### <a name="step-2---remove-the-online-voice-routing-policy-associated-with-your-user"></a>手順 2 - ユーザーに関連付けられているオンライン音声ルーティング ポリシーを削除する

番号が割り当てられていない場合は、次のTeams PowerShell モジュール コマンドを実行して、ユーザーに関連付けられているオンライン音声ルーティング ポリシーを削除します。

```PowerShell
Grant-CsOnlineVoiceRoutingPolicy -Identity <user> -PolicyName $Null
```

#### <a name="step-3---acquire-phone-numbers"></a>手順 3 - 電話番号を取得する

オペレーターの Web サイトに移動して、電話番号を注文して取得します。 オペレーターの Web サイトを見つけるには、[Microsoft 365 オペレーター接続 ディレクトリ](https://cloudpartners.transform.microsoft.com/practices/microsoft-365-for-operators/directory)を参照してください。 テナント ID を指定する必要があります。 テナント ID がわからない場合は、「[Microsoft 365 テナント ID を検索](/onedrive/find-your-office-365-tenant-id)する」を参照してください。

#### <a name="step-4---assign-phone-numbers"></a>手順 4 - 電話番号を割り当てる

オペレーターが注文を完了すると、番号がテナントにアップロードされます。 ボイス > 電話番号に移動すると、Teams管理センターで番号とプロバイダー **を** 表示できます。 Teams管理センターを使用するか、PowerShell を使用してオペレーター接続番号をユーザーに割り当てます。 詳細については、「番号の [割り当て](#assign-numbers)」を参照してください。

### <a name="assign-numbers"></a>番号を割り当てる

ユーザーに電話番号を割り当てる方法については、「ユーザーの電話番号を [割り当てる、変更する、または削除](assign-change-or-remove-a-phone-number-for-a-user.md)する」を参照してください。

## <a name="manage-your-operators"></a>オペレーターを管理する

[ **個人用演算子** ] タブから、演算子とその状態を表示し、選択内容に次の変更を加えることができます。  

- 国別にオペレーター サービスを管理する
- 演算子を中断する
- 演算子を削除する

> [!NOTE]
> 組織または国からオペレーターを削除する前に、組織または国のユーザーに割り当てられているすべての電話番号を削除し、オペレーターに連絡して番号を解放する必要があります。

## <a name="release-numbers"></a>リリース番号

Teams管理センターから電話番号を解放するには、**電話番号** ページに移動し、番号を選択します。

- 電話番号がユーザーに割り当てられていない場合は、[リリース] を選択 **します**。

- 電話番号がユーザーに割り当てられている場合は、番号の割り当てを解除する必要があります。 [ **編集]**、[ **ユーザーの削除]** の順に選択します。 変更を保存したら、[リリース] を選択 **します**。

## <a name="related-topics"></a>関連項目

- [自動応答と呼び出しキュー Teams計画する](plan-auto-attendant-call-queue.md)
