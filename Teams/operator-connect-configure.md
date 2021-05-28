---
title: オペレーター接続の構成
author: cazawideh
ms.author: czawideh
manager: serdars
ms.date: 04/12/2021
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
description: オペレーター接続を構成する方法の詳細については、以下を参照してください。
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: e82c862810448552bb9d2dc2d721815b5db43f55
ms.sourcegitcommit: 17e34d2de3d10f1d04929a695e301127db7014bd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/27/2021
ms.locfileid: "52689900"
---
# <a name="configure-operator-connect"></a>オペレーター接続の構成

>[!NOTE]
>Operator Connect は現在、パブリック プレビューでのみ **使用できます**。 パブリック プレビューでは、今後の機能をテストし、フィードバックを提供できます。 パブリック プレビューに含まれる機能は、完全ではなく、変更される可能性があります。また、Office 365 Government Clouds ではサポートされていません。

この記事では、Operator Connect を構成する方法について説明します。 オペレーター接続を構成する前に、前提条件とライセンスの詳細については、「 [オペレーター](operator-connect-plan.md) 接続の計画」を参照してください。

## <a name="enable-an-operator"></a>演算子を有効にする

Teams 管理センターでオペレーターを有効、編集、および削除できます。 左側のナビゲーション ウィンドウで、[Voice > **演算子] に移動します**。

演算子を有効にするには:

1. **演算子を選択します。** [すべての演算子 **] タブで** 、リージョンまたはサービス別に使用可能な演算子をフィルター処理して、音声ニーズに合った適切な演算子を見つけ出します。 次に、有効にする演算子を選択します。  

2. **国を選択します。** [ **演算子の設定]** で、選択した演算子で有効にする国を選択します。

3. **連絡先情報を指定します (省略可能)。** オペレーターからオペレーターに連絡して、オペレーターの接続に関する追加情報を知りたい場合は、チェック ボックスをオンにして連絡先情報を入力します。  

4. **データ転送に関する通知に同意します。**

5. **演算子を追加します。** [Add **as my operator]を選択して** 保存します。

## <a name="set-up-phone-numbers"></a>電話番号を設定する

電話番号の設定方法は、新規ユーザーの番号を設定するか、Microsoft 通話プランまたは直接ルーティングから既存の番号を移動するかによって異なります。

- 新しいユーザーの電話番号を取得する必要がある場合は、「新しい Teams ユーザーの [番号を取得する」を参照してください](#acquire-numbers-for-new-teams-users)。

- 通話プランからオペレーター接続に既存の番号を移動する場合は、「通話プランからオペレーター接続に番号を移動する [」を参照してください](#move-numbers-from-calling-plans-to-operator-connect)。

- 既存の番号を直接ルーティングからオペレーター接続に移動する場合は、「ダイレクト ルーティングからオペレーター接続に番号を移動 [する」を参照してください](#move-numbers-from-direct-routing-to-operator-connect)。

>[!IMPORTANT]
>**緊急対応の住所:** オペレーターから取得した番号に関連付けられている緊急対応の住所は、オペレーターと直接管理されます。 変更を加える場合は、オペレーターにお問い合わせください。

### <a name="acquire-numbers-for-new-teams-users"></a>新しい Teams ユーザーの番号を取得する

新しい Teams ユーザーの番号を取得するには、次の手順に従います。

1. **電話システム ライセンスを割り当てる。** 電話システム ライセンスは、Microsoft 365 管理センターまたは PowerShell を使用してユーザーに割り当てできます。 詳細については、「ユーザーに Teams アドオン [ライセンスを割り当てる」を参照してください](teams-add-on-licensing/assign-teams-add-on-licenses.md)。

2. **TeamsOnly モードを使用している必要があります。** 確認するには、Teams 管理センターで、[Teams のアップグレード] の [組織全体の **>に移動します**。 共存モードは Teams にのみ設定する必要があります。

3. **緊急対応の住所を作成して検証します。** Teams 管理センターで、[緊急対応の住所>の場所] に **移動して** 、緊急対応の住所を設定します。 詳細については、「組織の緊急対応の場所を追加、変更、または削除 [する」を参照してください](add-change-remove-emergency-location-organization.md)。

4. **数値を取得します。** オペレーターの Web サイトに移動して、電話番号を注文して取得します。 演算子 Web サイトの一覧については、「演算子」を [参照してください](#operators)。 テナント ID を指定する必要があります。 テナント ID が分からない場合は [、「Microsoft 365](/onedrive/find-your-office-365-tenant-id) テナント ID を検索する」を参照してください。

5. **数値を割り当てる。** オペレーターが注文を完了すると、テナントにテスト番号がアップロードされます。 [Voice > 電話番号] に移動すると、Teams 管理センター **で番号とプロバイダーを表示できます**。 Teams 管理センターを使用するか、PowerShell を使用してユーザーに番号を割り当てる。 詳細については、「番号を割り当てる [」を参照してください](#assign-numbers)。
 

### <a name="move-numbers-from-calling-plans-to-operator-connect"></a>通話プランからオペレーター接続に番号を移動する

1. オペレーターに問い合わせ、番号を Operator Connect に移植してください。 オペレーター [の Web](#operators) サイトを見つけるには、「演算子」を参照してください。

2. オペレーターが移植注文を完了したら、ユーザーの通話プランの電話番号の割り当てを解除し、通話プラン ライセンスを削除できます。 その後、オペレーターはテナントに番号をアップロードできます。

3. Teams 管理センターまたは PowerShell を使用して、オペレーター接続番号をユーザーに割り当てる。 詳細については、「番号を割り当てる [」を参照してください](#assign-numbers)。

 
### <a name="move-numbers-from-direct-routing-to-operator-connect"></a>ダイレクト ルーティングからオペレーター接続に番号を移動する

1. 次のように、ユーザーから既存の電話番号を削除します。  

   次の PowerShell コマンドを実行して、既存の On-prem Line URI を取得します。

   ```
   Get-CsOnlineUser -Identity <user> | select OnPremLineURI 
   ```

   次の PowerShell コマンドを実行して、On-prem Line URI を削除します。  

   ```
   Set-CsUser -identity <user> - OnPremLineURI $null 
   ```

2. ユーザーに関連付けられている PSTNUsage を削除します。それ以外の場合、通話は PSTN 使用法で指定されたゲートウェイにルーティングされます。 PSTN の使用状況を削除する方法については [、「Set-CsOnlinePstnUsage」を参照してください](/powershell/module/skype/set-csonlinepstnusage?view=skype-ps)。

3. オペレーターの Web サイトに移動して、電話番号を注文して取得します。 演算子 Web サイトの一覧については、「演算子」を [参照してください](#operators)。 テナント ID を指定する必要があります。 テナント ID が分からない場合は [、「Microsoft 365](/onedrive/find-your-office-365-tenant-id) テナント ID を検索する」を参照してください。

4. オペレーターが注文を完了すると、テナントにテスト番号がアップロードされます。 [Voice > 電話番号] に移動すると、Teams 管理センター **で番号とプロバイダーを表示できます**。 Teams 管理センターまたは PowerShell を使用して、オペレーター接続番号をユーザーに割り当てる。 詳細については、「番号を割り当てる [」を参照してください](#assign-numbers)。

   

### <a name="assign-numbers"></a>数値を割り当てる

新しい Teams ユーザーを追加する場合でも、既存のユーザーを Operator Connect に移動する場合でも、番号を割り当てる手順は次のとおりです。

Teams 管理センターを使用して番号を割り当てるには、[電話番号] に **移動します**。 手順は、通話プランの番号の割り当てと同じです。 詳細については、「ユーザーに電話番号 [を割り当てる」を参照してください](assign-change-or-remove-a-phone-number-for-a-user.md)。

PowerShell を使用して数値を割り当てるには、次Set-CsOnlineVoiceUserコマンドレットを使用します。

```
Set-CsOnlineVoiceUser -Identity <user>  -TelephoneNumber <phone number> 
```

次に例を示します。

```
Set-CsOnlineVoiceUser -Identity john@contoso.com -TelephoneNumber +14255550101
```

ユーザーに電話番号を割り当てる方法の詳細については、「ユーザーの電話番号を割り当て、変更、または削除する [」を参照してください](assign-change-or-remove-a-phone-number-for-a-user.md)。



## <a name="manage-your-operators"></a>オペレーターを管理する

[演算子] タブから、演算子とその状態を表示し、選択内容に次の変更を加えます。  

- 国別にオペレーター サービスを管理する
- 演算子を中断する
- 演算子を削除する

> [!NOTE]
> 組織または国からオペレーターを削除する前に、組織または国のユーザーに割り当てられているすべての電話番号を削除し、オペレーターに連絡して番号を解放する必要があります。

## <a name="operators"></a>オペレーター

次の演算子から電話番号を取得するには、ここにリンクされている Web サイトに移動します。


|オペレーター  |オペレーター Web サイト  |
|---------|---------|
|`BT`     |     https://www.globalservices.bt.com/en/aboutus/operator-connect        |
|`Deutsche Telekom`     |   https://cloud.telekom.de/de/blog/cloud-software/microsoft-teams-operator-connect      |
|`Intrado`     | https://insight.intrado.com/operator-connect       |
|`NTT`     |  https://www.hello.global.ntt/operator-connect       |
|`NuWave`     |   https://ipilot.io/microsoft-operator-connect/   |
|`Orange Business Services`     | https://www.orange-business.com/en/blogs/operator-connect-orange-and-microsoft-streamline-calling-for-teams-users        |
|`Pure IP`    | https://info.pure-ip.com/operator-connect        |
|`Rogers`    | https://www.rogers.com/business/products-and-solutions/microsoft-365-business-voice        |
|`TATA Communications`     |  https://www.tatacommunications.com/solutions/unified-communications/unified-communications-as-a-service/microsoft-teams-solutions/       |
|`Telenor`     | https://www.telenor.no/bedrift/telefoni/teams/operator-connect        |
|`Verizon`     |  https://www.verizon.com/business/resources/lp/operator-connect       |
