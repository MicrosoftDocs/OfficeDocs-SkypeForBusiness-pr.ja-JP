---
title: Teams Phone Mobile の構成
author: CarolynRowe
ms.author: crowe
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
description: Teams Phone Mobile を構成する方法の詳細について説明します。
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: e3e0e5c349610e9f8ad73b9b7a50b4c219304ea4
ms.sourcegitcommit: 179713dd2b22736c0d63060a6351eb69ec4abff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/12/2022
ms.locfileid: "68551681"
---
# <a name="configure-teams-phone-mobile"></a>Teams Phone Mobile の構成

Microsoft Teams 電話 Mobile プログラムに参加しているオペレーターとそのサービスが利用可能な国または地域の一覧については、「[Microsoft 365 Teams Phone Mobile](https://cloudpartners.transform.microsoft.com/practices/microsoft-365-for-operators/connect-mobile)」を参照してください。

この記事では、Teams Phone Mobile を構成する方法について説明します。 Teams Phone Mobile を構成する前に、利点、前提条件、およびライセンスの詳細については、「 [Teams Phone Mobile の計画](operator-connect-mobile-plan.md) 」を参照してください。

## <a name="enable-an-operator"></a>演算子を有効にする

Teams 管理センターでオペレーターを有効、編集、削除できます。 左側のナビゲーション ウィンドウで、[ **音声>演算子**] に移動します。

演算子を有効にするには:

1. Teams Phone Mobile をサポートするオペレーターを選択します。 [ **すべての演算子** ] タブで、利用可能なオペレーターをリージョンまたはサービス別にフィルター処理して、Teams Phone Mobile をサポートする適切なオペレーターを見つけます。 次に、有効にする演算子を選択します。

2. [ **オペレーターの設定**] で、選択した演算子で有効にする国を選択します。

3. **連絡先情報を入力します。** 完全な名前と電子メール アドレスを含む連絡先情報は、オペレーターと自動的に共有されます。 この情報は後で変更できます。 さらに、会社の規模を指定する必要があり、電話番号を入力することもできます。 オペレーターはこの情報を使用して、Teams Phone Mobile の詳細について連絡します。

4. データ転送に関する通知を受け入れます。

5. 保存 **する演算子として追加** を選択します。

## <a name="set-up-phone-numbers"></a>電話番号を設定する

既存の会社の有料 SIM 対応電話番号を Teams に追加する場合は、オペレーターに問い合わせて、対象となる Teams Phone Mobile サブスクリプションを持っていることを確認し、電話番号を Teams にアップロードできるようにします。 オペレーターが注文を完了したら、それらの番号をユーザーに割り当てることができます。 

オペレーターの Web サイトを見つけるには、 [Microsoft 365 Teams Phone Mobile ディレクトリ](https://cloudpartners.transform.microsoft.com/practices/microsoft-365-for-operators/directory)を参照してください。

テナント ID を指定する必要があります。 テナント ID がわからない場合は、「 [Microsoft 365 テナント ID を検索する](/onedrive/find-your-office-365-tenant-id.md)」を参照してください。 既存のデスク電話番号またはワイヤーライン番号が、お使いの地域およびオペレーターによってサポートされている場合は、ワイヤレス音声サブスクリプションに移植している可能性があります。 

電話番号の設定方法は、新しいユーザーの番号を設定するか、Microsoft 通話プラン、オペレーター接続、または直接ルーティングから既存の番号を移動するかによって異なります。

- [新しい Teams ユーザーの番号を取得します](#acquire-numbers-for-new-teams-users)。  

- [通話プランから Teams Phone Mobile に番号を移動します](#move-numbers-from-calling-plans-to-teams-phone-mobile)。  

- [オペレーター接続から Teams Phone Mobile に番号を移動](#move-numbers-from-operator-connect-to-teams-phone-mobile)します。  

- [直接ルーティングから Teams Phone Mobile に番号を移動](#move-numbers-from-direct-routing-to-teams-phone-mobile)します。  


### <a name="assign-numbers-to-emergency-addresses"></a>緊急時の住所に番号を割り当てる

緊急対応アドレスは、Microsoft Teams エンドポイント/クライアントからアクセスできる場合に、番号に関連付けられた静的な場所です。 Teams 管理センターで緊急対応の住所を作成した後、アドレスの割り当て方法、または後で変更する方法は、オペレーターによって異なります。

Microsoft Teams エンドポイントで使用されている緊急アドレスに番号を割り当てるには、オペレーターは次の 3 つのシナリオのいずれかを実装します。

- オペレーターは電話番号に緊急アドレスを割り当て、後で Teams 管理センターで変更できます。

- オペレーターはアドレスを割り当てず、Teams 管理センターの電話番号に緊急対応の住所を割り当てることができます。

- オペレーターは電話番号に緊急対応の住所を割り当て、それを変更することはできません。 このシナリオでは、電話番号と割り当てられた緊急対応の住所を変更するには、オペレーターに連絡する必要があります。

SIM 対応スマートフォンのネイティブ ダイヤラーを介して通話が行われる場合、オペレーターは、緊急対応のおおよその場所への呼び出しを処理する地理的座標またはセル タワーを使用してサポートを受けることができます。

緊急通報の詳細については、「緊急通報の管理と動的 [緊急通報](what-are-emergency-locations-addresses-and-call-routing.md) の [計画と構成](configure-dynamic-emergency-calling.md)」を参照してください。

### <a name="acquire-numbers-for-new-teams-users"></a>新しい Teams ユーザーの番号を取得する

新しい Teams ユーザーの番号を取得するには、次の手順に従います。

1. **電話システム ライセンスと Teams Phone Mobile アドオン ライセンスを割り当てます。** 電話システム ライセンスと Teams Phone Mobile アドオン ライセンスは、Microsoft 365 管理センターまたは PowerShell を使用してユーザーに割り当てることができます。 詳細については、「 [Teams アドオン ライセンスをユーザーに割り当てる」を参照してください](teams-add-on-licensing/assign-teams-add-on-licenses.md)。

2. **Teams Phone Mobile で取得した電話番号を割り当てるユーザーは、TeamsOnly モードである必要があります。** 組織が TeamsOnly モードの場合は、すべてのユーザーが TeamsOnly モードになります。 

   確認するには、Teams 管理センターで **Teams > Teams のアップグレード設定** に移動します。 組織がアイランド モードの場合は、特定のユーザーが TeamsOnly モードであるかどうかを確認します。 **[ユーザー]** に移動し、ユーザー アカウントを選択します。 [ **アカウント** ] タブの [ **Teams のアップグレード** ] で、共存モードを TeamsOnly に設定する必要があります。

3. **数値を取得します。** オペレーターの Web サイトに移動するか、Teams Phone Mobile サービスが有効になっているモバイル SIM 対応電話番号を注文して取得します。 

   オペレーターが注文を完了すると、SIM 対応の携帯電話番号がテナントにアップロードされます。 **Voice >の電話番号** に移動すると、Teams 管理センターで番号とプロバイダーを表示できます。 

4. **番号を割り当てます。** Teams 管理センターまたは PowerShell を使用して、ユーザーに番号を割り当てることができます。 詳細については、「番号の [割り当て](assign-change-or-remove-a-phone-number-for-a-user.md)」を参照してください。

### <a name="move-numbers-from-calling-plans-to-teams-phone-mobile"></a>通話プランから Teams Phone Mobile に番号を移動する

1. Teams Phone Mobile および Teams Phone Mobile アドオン ライセンスの対象となる Microsoft 365 サブスクリプションがあることを確認します。 [移動する電話番号は、それぞれのユーザーに対して削除する必要があります](assign-change-or-remove-a-phone-number-for-a-user.md#remove-a-phone-number-from-a-user)。 

2. SIM 対応の対象ワイヤレス音声プランで Teams Phone Mobile に番号を移植するには、オペレーターに問い合わせてください。 

3. オペレーターが移植順序を完了すると、オペレーターはテナントに番号をアップロードします。  **Voice >の電話番号** に移動すると、Teams 管理センターで番号とプロバイダーを表示できます。 

4. Teams 管理センターを使用するか、PowerShell を使用して、ユーザーに番号を割り当てることができます。 詳細については、「番号の [割り当て](assign-change-or-remove-a-phone-number-for-a-user.md)」を参照してください。

### <a name="move-numbers-from-operator-connect-to-teams-phone-mobile"></a>オペレーター接続から Teams Phone Mobile に番号を移動する

1. Teams Phone Mobile および Teams Phone Mobile アドオン ライセンスの対象となる Microsoft 365 サブスクリプションがあることを確認します。 [移動する電話番号は、それぞれのユーザーに対して削除する必要があります](assign-change-or-remove-a-phone-number-for-a-user.md#remove-a-phone-number-from-a-user)。 テナントから電話番号を削除するには、既存のオペレーター接続プロバイダーに問い合わせてください。

2. SIM 対応の対象ワイヤレス音声プランで Teams Phone Mobile に番号を移植するには、オペレーターに問い合わせてください。 

3. オペレーターが移植順序を完了すると、オペレーターはテナントに番号をアップロードします。 **Voice >の電話番号** に移動すると、Teams 管理センターで番号とプロバイダーを表示できます。 

4. Teams 管理センターを使用するか、PowerShell を使用して、ユーザーに番号を割り当てることができます。 詳細については、「番号の [割り当て](assign-change-or-remove-a-phone-number-for-a-user.md)」を参照してください。

### <a name="move-numbers-from-direct-routing-to-teams-phone-mobile"></a>直接ルーティングから Teams Phone Mobile に番号を移動する   

直接ルーティングから Teams Phone Mobile に番号を移動するには、次の手順を完了する必要があります。

1. [既存のダイレクト ルーティング番号がオンラインまたはオンプレミスに割り当てられているかどうかを確認します](#determine-if-the-existing-direct-routing-numbers-are-assigned-online-or-on-premises)。

2. [直接ルーティングから Teams Phone Mobile に番号を移行](#migrate-the-numbers-from-direct-routing-to-teams-phone-mobile)します。

2. [ユーザーに関連付けられているオンライン音声ルーティング ポリシーを削除します](#remove-the-online-voice-routing-policy-associated-with-your-user)。

3. [電話番号を取得します](#acquire-phone-numbers)。

4. [電話番号を割り当てます](#assign-phone-numbers)。

これらの手順については、以降のセクションで詳しく説明します。

#### <a name="determine-if-the-existing-direct-routing-numbers-are-assigned-online-or-on-premises"></a>既存のダイレクト ルーティング番号がオンラインまたはオンプレミスに割り当てられているかどうかを確認します。

既存のダイレクト ルーティング番号を削除する方法は、その番号がオンプレミスとオンラインのどちらに割り当てられているかによって異なります。

1. まず、次の Teams PowerShell コマンドを実行して、ユーザーに直接ルーティング番号が割り当てられていることを確認します。 NumberType は DirectRouting である必要があります。

   ```PowerShell
   Get-CsPhoneNumberAssignment -AssignedPstnTargetId <user> 
   ```

2. 次の Teams PowerShell コマンドを実行して、番号がオンラインまたはオンプレミスのどちらに割り当てられているかを確認します。

   ```PowerShell
   Get-CsOnlineUser -Identity <user> | fl RegistrarPool, OnPremLineURI, LineURI 
   ```

   OnPremLineUri に E.164 電話番号が設定されている場合、電話番号はオンプレミスに割り当てられ、Microsoft 365 に同期されました。

#### <a name="migrate-the-numbers-from-direct-routing-to-teams-phone-mobile"></a>直接ルーティングから Teams Phone Mobile に番号を移行する

番号を移行するには、次の手順に従います。  

> [!Important]
> 移行中、電話番号は使用できなくなります。 移行を開始する前に、Teams Phone Mobile オペレーターと調整します。

- **オンラインで割り当てられている既存のダイレクト ルーティング番号を Teams Phone Mobile に移行するには**、オペレーターに問い合わせてください。 オペレーターの Web サイトを見つけるには、 [Microsoft 365 Teams Phone Mobile ディレクトリ](https://cloudpartners.transform.microsoft.com/practices/microsoft-365-for-operators/directory)に関するページを参照してください。 合意された日時に、オペレーターは番号を直接ルーティングから Teams Phone Mobile に移行します。 これには、テナントから移行する電話番号を削除し、Teams Phone Mobile に関連付けられている新しい電話番号として再度追加することが含まれる場合があります。

- **オンプレミスに割り当てられているダイレクト ルーティング番号を Teams Phone Mobile に移行するには**、次のSkype for Business Server PowerShell コマンドを実行します。

   ```PowerShell
   Set-CsUser -Identity <user> -LineURI $null 
   ```
  オンプレミス番号が削除され、変更がオンプレミスから Microsoft 365 に同期されているかどうかを確認するには、次の Teams PowerShell コマンドを実行します。

   ```PowerShell
   Get-CsOnlineUser -Identity <user> | fl RegistrarPool, OnPremLineURI, LineURI 
   ```

変更が Microsoft 365 オンライン ディレクトリに同期された後、予想される出力は次のようになります。

```
ConsoleCopy
RegistrarPool                        : pool.infra.lync.com
OnPremLineURI                        : 
LineURI                              
```

電話番号が削除されたかどうかを確認するには、次の Teams PowerShell コマンドを実行します。

```PowerShell
Get-CsOnlineUser -Identity <user> | fl LineUri
```

> [!NOTE]
> 削除が有効になるまでにかかる時間は、構成によって異なります。 電話番号の削除には最大 10 分かかる場合があります。まれに、最大で 24 時間かかる場合があります。 

#### <a name="remove-the-online-voice-routing-policy-associated-with-your-user"></a>ユーザーに関連付けられているオンライン音声ルーティング ポリシーを削除する

番号が割り当てられていない場合は、次の Teams PowerShell コマンドを実行して、ユーザーに関連付けられているオンライン音声ルーティング ポリシーを削除します。

```PowerShell
Grant-CsOnlineVoiceRoutingPolicy -Identity <user> -PolicyName $Null
```

#### <a name="acquire-phone-numbers"></a>電話番号を取得する

SIM 対応の対象ワイヤレス音声プランで Teams Phone Mobile に番号を移植するには、オペレーターに問い合わせてください。

オペレーターが注文を完了すると、番号がテナントにアップロードされます。 **Voice >の電話番号** に移動すると、Teams 管理センターで番号とプロバイダーを表示できます。 

#### <a name="assign-phone-numbers"></a>電話番号を割り当てる

Teams 管理センターを使用するか、PowerShell を使用して Teams Phone 携帯電話番号をユーザーに割り当てることができます。 詳細については、「番号の [割り当て](assign-change-or-remove-a-phone-number-for-a-user.md)」を参照してください。


## <a name="manage-your-operators"></a>オペレーターを管理する

[ **個人用演算子** ] タブから、演算子とその状態を表示し、選択内容に次の変更を加えることができます。  

- 国別にオペレーター サービスを管理する
- 演算子を中断する
- 演算子を削除する

> [!NOTE]
> 組織または国からオペレーターを削除する前に、組織または国のユーザーに割り当てられているすべての電話番号を削除し、オペレーターに連絡して番号を解放する必要があります。

## <a name="release-numbers"></a>リリース番号

Teams 管理センターから電話番号を解放するには、[電話番号] ページに移動し、 **番号** を選択します。

- 電話番号がユーザーに割り当てられていない場合は、[リリース] を選択 **します**。

- 電話番号がユーザーに割り当てられている場合は、番号の割り当てを解除する必要があります。 [ **編集]**、[ **ユーザーの削除]** の順に選択します。 変更を保存したら、[リリース] を選択 **します**。

## <a name="manage-user-incoming-calling-policies"></a>ユーザー着信通話ポリシーを管理する

Teams 管理センターを使用するか、PowerShell を使用して、ユーザーの着信通話ポリシーを管理できます。 既定では、Teams Phone Mobile ユーザーの着信呼び出しは、ユーザーの SIM 対応モバイル デバイスで最初に Teams アプリを呼び出します。 

- ユーザーの着信通話設定が Teams アプリに設定されている場合、すべての着信呼び出しは、SIM 対応スマートフォン上の Teams アプリと、他のデバイス上の他の Teams エンドポイントを同時に呼び出します。 

- ユーザーの着信通話設定がネイティブ ダイヤラーに設定されている場合、すべての着信通話は SIM 対応スマートフォンのネイティブ ダイヤラーを呼び出し、他のデバイス上の他のすべての Teams エンドポイントを同時に呼び出します。 

### <a name="use-the-teams-admin-center"></a>Teams 管理センターを使用する

Teams 管理センターを使用してユーザーの着信通話ポリシーを管理するには::

1. [音声] タブで、[ **モビリティ ポリシー**] を選択します。 

2. 新しいモバイル ポリシーを追加するには、[ **追加**] をクリックします。

3. 名前を選択し、ポリシーの説明を追加し、[ **モバイル ダイヤラーの選択** ] ドロップダウン オプションから次のいずれかを選択します。

   -  **Microsoft Teams は** 、最初に SIM 対応スマートフォンで Teams アプリを呼び出します。 

   - **最初** に SIM 対応スマートフォンでネイティブ ダイヤラーを呼び出すネイティブ ダイヤラー。

4. ポリシーをユーザーに割り当てます。 [「ポリシーの割り当て](assign-policies-users-and-groups.md)」を参照してください。


### <a name="use-powershell"></a>PowerShell を使用する

1. テナントに接続する: Connect-MicrosoftTeams。
 
2. ネイティブ ダイヤラーまたは Teams アプリを最初に呼び出す着信呼び出しのポリシーを作成します。 (ポリシー名を選択できます。この例では TeamsFirst と NativeFirst を使用します)。 

   ```PowerShell
   New-CsTeamsMobilityPolicy -identity TeamsFirst -MobileDialerPreference Teams 
   New-CsTeamsMobilityPolicy -identity NativeFirst -MobileDialerPreference Native 
   ```

3. ユーザーにポリシーを付与する: 

   ```PowerShell
   Grant-CsTeamsMobilityPolicy NativeFirst -Identity user@xyz.onmicrosoft.com
   Grant-CsTeamsMobilityPolicy TeamsFirst -Identity user@xyz.onmicrosoft.com
   ```

4. ユーザー ポリシーを確認します。 

   ```PowerShell
   get-CsUserpolicyassignment -identity user@xyz.onmicrosoft.com
   ```
 
 5. すべてのモビリティ ポリシー オプションを確認します。 
    
    ```PowerShell
    Get-CsTeamsMobilityPolicy
    ```  

 








