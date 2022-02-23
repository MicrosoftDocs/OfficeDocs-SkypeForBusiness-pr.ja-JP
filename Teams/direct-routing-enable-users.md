---
title: ユーザーに直接ルーティングを有効にする
ms.reviewer: filippse
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: ダイレクト ルーティングでユーザーを有効にするMicrosoft Teams 電話説明します。
ms.openlocfilehash: be2f0e0f33bd236591c8c8a2d9cf415972e018d6
ms.sourcegitcommit: e9b0a274fdfee3d5bc8211cb099155546b281fe0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2022
ms.locfileid: "62926300"
---
# <a name="enable-users-for-direct-routing"></a>ユーザーに直接ルーティングを有効にする

この記事では、ユーザーが直接ルーティングを有効にする方法について説明します。 これは、ダイレクト ルーティングを構成するための次の手順の手順 2 です。

- 手順 1. [Connectを使用して SBC を電話システムし、接続を検証する](direct-routing-connect-the-sbc.md) 
- **手順 2.ダイレクト ルーティングのユーザーを有効にする**   (この記事)
- 手順 3. [音声ルーティングを構成する](direct-routing-voice-routing.md)
- 手順 4. [数値を別の形式に変換する](direct-routing-translate-numbers.md) 


ダイレクト ルーティングを設定するために必要なすべての手順については、「ダイレクト ルーティングの構成 [」を参照してください](direct-routing-configure.md)。

ユーザーが直接ルーティングを有効にする準備ができたら、次の手順に従います。 

1. アプリでユーザーを作成Microsoft 365ライセンスを割り電話システムします。  
2. ユーザーがオンラインでホームに設定されている必要があります。
3. 電話番号を構成し、エンタープライズ音声を有効にする。 
4. ユーザーにTeamsのみモードを割り当てる。

## <a name="create-a-user-and-assign-the-license"></a>ユーザーを作成してライセンスを割り当てる

新しいユーザーを作成するには、2 つのオプションMicrosoft 365。 ただし、ルーティングの問題を回避するために、組織で 1 つのオプションを選択する必要があります。 

- オンプレミスの Active Directory にユーザーを作成し、そのユーザーをクラウドと同期します。 「[オンプレミスのディレクトリとオンプレミスのディレクトリを統合する」Azure Active Directory](/azure/active-directory/connect/active-directory-aadconnect)。
- ユーザーを作成するには、Microsoft 365 管理センター。 「[ユーザーを個別に、または一括でユーザーを追加する」Microsoft 365または Office 365 - 管理者向けヘルプ] を参照してください](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec)。 

Skype for Business Online の展開がオンプレミスの Skype for Business 2015 または Lync 2010 または 2013 と共存している場合、サポートされる唯一のオプションは、オンプレミスの Active Directory でユーザーを作成し、ユーザーをクラウドと同期することだけです (オプション 1)。 

ライセンス要件の詳細については、「直接ルーティングの計画」の「ライセンスと[他の](direct-routing-plan.md#licensing-and-other-requirements)[要件」を参照してください](direct-routing-plan.md)。

## <a name="ensure-that-the-user-is-homed-online"></a>ユーザーがオンラインでホームに設定されている 

この手順は、有効Skype for Business Server エンタープライズ VoIPユーザーが直接ルーティングに移行Teamsに適用されます。

ダイレクト ルーティングでは、ユーザーをオンラインでホームに設定する必要があります。 RegistrarPool パラメーターを確認すると確認できます。このパラメーターには、infra.lync.com があります。 Microsoft では、ユーザーを直接ルーティングに移行するときに、LineURI をオンプレミスからオンラインに変更Teams必要とします。 

1. Connect PowerShell Microsoft Teamsを作成します。

2. コマンドを発行します。 

    ```PowerShell
    Get-CsOnlineUser -Identity "<User name>" | fl RegistrarPool,OnPremLineUriManuallySet,OnPremLineUri,LineUri
    ``` 
    OnPremLineUriManuallySet が False に設定され、LineUri に <E.164 電話番号> が設定されている場合、電話番号はオンプレミスに割り当て済みであり、Microsoft 365 に同期されます。 電話番号をオンラインで管理する場合は、Teams PowerShell を使用して電話番号を構成する前に、オンプレミスの Skype for Business Management Shell を使用してパラメーターをクリーンアップし、Microsoft 365 に同期します。 

1. 管理Skype for Businessから、次のコマンドを発行します。 

   ```PowerShell
   Set-CsUser -Identity "<User name>" -LineUri $null
    ``` 
 > [!NOTE]
 > EnterpriseVoiceEnabled を False に設定する必要はありません。レガシ Skype for Business 電話が使用され、テナント ハイブリッド構成が UseOnPremDialPlan $True で設定されている場合、ダイヤル プランの正規化の問題が発生する可能性があります。 
    
   変更が同期された後、 のMicrosoft 365の出力は`Get-CsOnlineUser -Identity "<User name>" | fl RegistrarPool,OnPremLineUriManuallySet,OnPremLineUri,LineUri`次の結果です。

   ```console
   RegistrarPool                        : pool.infra.lync.com
   OnPremLineURIManuallySet             : True
   OnPremLineURI                        : 
   LineURI                              : 
   ```
 > [!NOTE]
 > オンプレミスの電話環境を削除する前に、すべてのユーザーの電話属性をオンライン[で管理Skype for Businessがあります](/skypeforbusiness/hybrid/decommission-on-prem-overview)。 

## <a name="configure-the-phone-number-and-enable-enterprise-voice"></a>電話番号を構成し、エンタープライズ音声を有効にする 

ユーザーを作成し、ライセンスを割り当てた後は、ユーザーのオンライン電話設定を構成する必要があります。 ユーザーに対する クラウド ボイスメールの構成は自動的に行われるので、追加の構成を行う必要はありません。

電話番号は、管理センターの管理者Teams PowerShell を使用してTeamsできます。

### <a name="use-teams-admin-center"></a>管理Teams使用する

1. [ユーザー管理 **] に** -> **移動します**。

2. ユーザーを選択します。

2. [アカウント **の全般情報****] で、[** 編集] を **選択します**。

3. [**電話番号の割り当** て] で、[電話番号電話 **の種類**] ドロップダウン メニューから [直接ルーティング] **を選択します**。

4. 割り当てられた電話番号と電話番号の内線番号 (該当する場合) を入力します。

5. [適用] **を選択します。**

アカウントの全般情報に、割り当てられた電話番号と直接ルーティングが電話番号の種類として表示されます。


### <a name="use-powershell"></a>PowerShell を使用する

1. Connect PowerShell セッションMicrosoft Teamsに接続します。 

2. 次の手順は、ユーザーの電話番号をオンプレミスかオンラインかを管理しているかによって異なっています。 オンプレミスで電話番号を管理している場合は、オンプレミスの Skype for Business Management Shell、コントロール パネル、または「分離後に属性を管理する方法を決定する」で説明されている方法[](/skypeforbusiness/hybrid/cloud-consolidation-managing-attributes)のいずれかを使用する必要があります。

   - ユーザーの電話番号をオンプレミスで管理している場合は、次のコマンドを使用して、ユーザーがオンラインエンタープライズ VoIP有効になっている必要があります。

       ```PowerShell
       Set-CsPhoneNumberAssignment -Identity "<User name>" -EnterpriseVoiceEnabled $true
       ```
       
   - ユーザーの電話番号をオンラインで管理している場合は、PowerShell の次のコマンドを使用して、ユーザーに電話番号を割り当Teamsがあります。 ユーザーは、 コマンドエンタープライズ VoIP自動的に有効になります。 
 
       ```PowerShell
       Set-CsPhoneNumberAssignment -Identity "<User name>" -PhoneNumber <phone number> -PhoneNumberType DirectRouting
       ```
    
       たとえば、ユーザー "Spencer Low" の電話番号を追加するには、次を入力します。 

       ```PowerShell
       Set-CsPhoneNumberAssignment -Identity "spencer.low@contoso.com" -PhoneNumber "+14255388797" -PhoneNumberType DirectRouting
       ```
       ユーザー "Spencer Low" と "Stacy Quinn" が一意の拡張子を持つ同じ基本番号を共有している場合は、次を入力します。
    
       ```PowerShell
       Set-CsPhoneNumberAssignment -Identity "spencer.low@contoso.com" -PhoneNumber "+14255388701;ext=1001" -PhoneNumberType DirectRouting
       Set-CsPhoneNumberAssignment -Identity "stacy.quinn@contoso.com" -PhoneNumber "+14255388701;ext=1002" -PhoneNumberType DirectRouting
       ```

    Microsoft では、電話番号が国コードを含む完全な E.164 電話番号として構成されていることを推奨していますが、必要はありません。 内線番号を使用して電話番号を構成できます。 これらの拡張機能は、ベース番号に対する参照が複数の結果を返す場合にユーザーを検索するために使用されます。 この機能により、会社は同じ基本番号と一意の内線番号を持つ電話番号を構成できます。 ルックアップを成功するには、次のように、招待に拡張子を含む完全な番号を含める必要があります。
    
    ```PowerShell
    To: <sip:+14255388701;ext=1001@sbc1.adatum.biz
    ```


## <a name="configure-sending-calls-directly-to-voicemail"></a>ボイスメールへの通話の直接送信を構成する

ダイレクト ルーティングを使用すると、ユーザーへの呼び出しを終了し、ユーザーのボイスメールに直接送信できます。 通話をボイスメールに直接送信する場合は、opaque=app:voicemail を Request URI ヘッダーに添付します。 たとえば、"sip:user@yourdomain.com;opaque=app:voicemail" などです。 ユーザー Teams呼び出し通知を受信しない場合、通話はユーザーのボイスメールに直接接続されます。

## <a name="assign-teams-only-mode-to-users-to-ensure-calls-land-in-microsoft-teams"></a>ユーザーに Teams モードを割り当て、通話が確実に着信Microsoft Teams

直接ルーティングでは、ユーザーが着信Teamsクライアントに着信通話が確実に着信Teams必要があります。 ユーザーを [のみ] Teamsするには、TeamsUpgradePolicy の "UpgradeToTeams" インスタンスを割り当てる必要があります。 詳細については、「IT 管理者向け [アップグレード戦略」を参照してください](upgrade-to-teams-on-prem-implement.md)。 組織で Skype for Business Server を使用している場合、Skype と Teams の間の相互運用性については、Skype for Business との移行と相互運用性に関する記事[を参照してください](migration-interop-guidance-for-teams-with-skype.md)。

## <a name="see-also"></a>関連項目

[ダイレクト ルーティングを計画する](direct-routing-plan.md)

[ダイレクト ルーティングを構成する](direct-routing-configure.md)
