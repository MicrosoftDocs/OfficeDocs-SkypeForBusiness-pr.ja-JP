---
title: ダイレクト ルーティングのユーザーを有効にする
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
description: ユーザーがダイレクト ルーティングをMicrosoft Teams 電話できるようにする方法について説明します。
ms.openlocfilehash: e82865abcc7bb37835009fb9ab7f93e11c423d66
ms.sourcegitcommit: b91d83739a078b175770c797c17d602eb5c83a4f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2022
ms.locfileid: "63774096"
---
# <a name="enable-users-for-direct-routing"></a>ダイレクト ルーティングのユーザーを有効にする

この記事では、ユーザーがダイレクト ルーティングを有効にする方法について説明します。 これは、ダイレクト ルーティングを構成するための次の手順の手順 2 です。

- 手順 1. [電話システムで SBC をConnectし、接続を検証する](direct-routing-connect-the-sbc.md) 
- **手順 2.ダイレクト ルーティングのユーザーを有効にする**   (この記事)
- 手順 3. [音声ルーティングを構成する](direct-routing-voice-routing.md)
- 手順 4. [数値を別の形式に変換する](direct-routing-translate-numbers.md) 


ダイレクト ルーティングの設定に必要なすべての手順については、「ダイレクト ルーティングの [構成」を参照してください](direct-routing-configure.md)。

ダイレクト ルーティングのユーザーを有効にする準備ができたら、次の手順に従います。 

1. Microsoft 365でユーザーを作成し、電話システム ライセンスを割り当てます。  
2. ユーザーがオンラインになっていることを確認します。
3. 電話番号を構成し、エンタープライズ音声を有効にします。 
4. ユーザーにTeamsのみモードを割り当てます。

## <a name="create-a-user-and-assign-the-license"></a>ユーザーを作成し、ライセンスを割り当てる

Microsoft 365で新しいユーザーを作成するには、2 つのオプションがあります。 ただし、Microsoft では、ルーティングの問題を回避するために、組織で 1 つのオプションを選択することをお勧めします。 

- オンプレミスの Active Directoryでユーザーを作成し、ユーザーをクラウドに同期します。 「[オンプレミス ディレクトリとAzure Active Directoryを統合する」を参照してください](/azure/active-directory/connect/active-directory-aadconnect)。
- Microsoft 365 管理センターで直接ユーザーを作成します。 Microsoft 365[またはOffice 365にユーザーを個別または一括で追加する - 管理者向けヘルプ](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec)を参照してください。 

Skype for Business Online 展開がSkype for Business 2015 または Lync 2010 または 2013 オンプレミスと共存する場合、サポートされているオプションは、オンプレミスの Active Directoryでユーザーを作成し、ユーザーをクラウドに同期することです (オプション 1)。 

ライセンス要件の詳細については、「[プラン ダイレクト ルーティング](direct-routing-plan.md)」の[ライセンスとその他の要件](direct-routing-plan.md#licensing-and-other-requirements)に関するページを参照してください。

## <a name="ensure-that-the-user-is-homed-online"></a>ユーザーがオンラインであることを確認する 

この手順は、Teams ダイレクト ルーティングに移行される有効なユーザー Skype for Business Server エンタープライズ VoIPに適用されます。

ダイレクト ルーティングでは、ユーザーがオンラインでホームになっている必要があります。 infra.lync.com ドメインに値が必要な RegistrarPool パラメーターを調べて確認できます。 Microsoft では、ユーザーを Teams ダイレクト ルーティングに移行するときに、LineURI をオンプレミスからオンラインに変更することを推奨していますが、必須ではありません。 

1. Microsoft Teams PowerShell セッションをConnectします。

2. コマンドを発行します。 

    ```PowerShell
    Get-CsOnlineUser -Identity "<User name>" | fl RegistrarPool,OnPremLineUri,LineUri
    ``` 
    OnPremLineUri に<E.164 電話番号>が設定されている場合、電話番号はオンプレミスに割り当てられ、Microsoft 365に同期されました。 オンラインで電話番号を管理する場合は、オンプレミスのSkype for Business管理シェルを使用してパラメーターをクリーニングし、Microsoft 365に同期してから、powerShell Teams使用して電話番号を構成します。 

1. 管理シェルSkype for Businessから、次のコマンドを発行します。 

   ```PowerShell
   Set-CsUser -Identity "<User name>" -LineUri $null
    ``` 
 > [!NOTE]
 > 必須がないため、EnterpriseVoiceEnabled を False に設定しないでください。レガシ Skype for Business電話が使用中で、テナント ハイブリッド構成が UseOnPremDialPlan $Trueで設定されている場合、ダイヤル プランの正規化の問題が発生する可能性があります。 
    
   変更がMicrosoft 365に同期された後、予想される出力`Get-CsOnlineUser -Identity "<User name>" | fl RegistrarPool,OnPremLineUriManuallySet,OnPremLineUri,LineUri`は次のようになります。

   ```console
   RegistrarPool                        : pool.infra.lync.com
   OnPremLineURIManuallySet             : True
   OnPremLineURI                        : 
   LineURI                              : 
   ```
 > [!NOTE]
 > オンプレミスのSkype for Business[環境をデコミッション](/skypeforbusiness/hybrid/decommission-on-prem-overview)する前に、すべてのユーザーの電話属性をオンラインで管理する必要があります。 

## <a name="configure-the-phone-number-and-enable-enterprise-voice"></a>電話番号を構成し、エンタープライズ音声を有効にする 

ユーザーを作成してライセンスを割り当てた後、ユーザーのオンライン電話設定を構成する必要があります。 ユーザーのクラウド ボイスメールの構成は自動的に行われます。追加の構成を行う必要はありません。

電話番号は、Teams管理センターを使用するか、powerShell Teams使用して構成できます。

### <a name="use-teams-admin-center"></a>管理センター Teams使用する

1. **UsersManage** ->  ユーザーに移動 **します**。

2. ユーザーを選択します。

2. [**アカウント****の全般情報**] で、[編集] を選択 **します**。

3. [**電話番号の割り当て**] **で、[電話番号の種類**] ドロップダウン メニューから [**ダイレクト ルーティング**] を選択します。

4. 割り当てられた電話番号と電話番号の内線番号 (該当する場合) を入力します。

5. [適用] を選択 **します。**

アカウントの一般的な情報に、割り当てられた電話番号と直接ルーティングが電話番号の種類として表示されます。


### <a name="use-powershell"></a>PowerShell を使用する

1. Microsoft Teams PowerShell セッションにConnectします。 

2. 次の手順は、ユーザーの電話番号をオンプレミスとオンラインのどちらで管理しているかによって異なります。 電話番号をオンプレミスで管理している場合は、「デ[コミット後に属性](/skypeforbusiness/hybrid/cloud-consolidation-managing-attributes)を管理する方法を決定する」で説明されている方法の 1 つ、またはオンプレミス Skype for Business管理シェル、コントロール パネル、またはいずれかの方法を使用する必要があります。

   - ユーザーの電話番号をオンプレミスで管理している場合は、次のコマンドを使用して、ユーザーがオンラインで有効エンタープライズ VoIPことを確認する必要があります。

       ```PowerShell
       Set-CsPhoneNumberAssignment -Identity "<User name>" -EnterpriseVoiceEnabled $true
       ```
       
   - ユーザーの電話番号をオンラインで管理している場合は、PowerShell で次のコマンドを使用してユーザーに電話番号Teams割り当てる必要があります。 ユーザーは、コマンドによって自動的に有効エンタープライズ VoIP。 
 
       ```PowerShell
       Set-CsPhoneNumberAssignment -Identity "<User name>" -PhoneNumber <phone number> -PhoneNumberType DirectRouting
       ```
    
       たとえば、ユーザー "Spencer Low" の電話番号を追加するには、次のように入力します。 

       ```PowerShell
       Set-CsPhoneNumberAssignment -Identity "spencer.low@contoso.com" -PhoneNumber "+14255388797" -PhoneNumberType DirectRouting
       ```
       ユーザー "Spencer Low" と "Stacy Quinn" が一意の拡張機能と同じ基本番号を共有している場合は、次のように入力します。
    
       ```PowerShell
       Set-CsPhoneNumberAssignment -Identity "spencer.low@contoso.com" -PhoneNumber "+14255388701;ext=1001" -PhoneNumberType DirectRouting
       Set-CsPhoneNumberAssignment -Identity "stacy.quinn@contoso.com" -PhoneNumber "+14255388701;ext=1002" -PhoneNumberType DirectRouting
       ```

    Microsoft では、電話番号を国番号を含む完全な E.164 電話番号として構成することをお勧めしますが、必須ではありません。 内線番号を使用して電話番号を構成できます。 これらの拡張機能は、ベース番号に対する参照が複数の結果を返すときに、ユーザーを検索するために使用されます。 この機能により、会社は同じ基本番号と一意の拡張機能を使用して電話番号を構成できます。 参照を成功させるには、次のように、招待に拡張子を含む完全な番号を含める必要があります。
    
    ```PowerShell
    To: <sip:+14255388701;ext=1001@sbc1.adatum.biz
    ```


## <a name="configure-sending-calls-directly-to-voicemail"></a>ボイスメールに直接通話を送信するように構成する

ダイレクト ルーティングを使用すると、ユーザーへの呼び出しを終了し、ユーザーのボイスメールに直接送信できます。 通話をボイスメールに直接送信する場合は、OPAQUE=app:ボイスメールを Request URI ヘッダーにアタッチします。 たとえば、"sip:user@yourdomain.com;opaque=app:ボイスメール" などです。 Teams ユーザーは通話通知を受け取りません。通話はユーザーのボイスメールに直接接続されます。

## <a name="assign-teams-only-mode-to-users-to-ensure-calls-land-in-microsoft-teams"></a>Teamsのみモードをユーザーに割り当てて、通話が確実にMicrosoft Teams

ダイレクト ルーティングでは、着信呼び出しがTeams クライアントに確実に到着するように、ユーザーがTeamsのみモードになっている必要があります。 ユーザーをTeamsのみモードにするには、TeamsUpgradePolicy の "UpgradeToTeams" インスタンスを割り当てます。 詳細については、「 [IT 管理者向けのアップグレード戦略](upgrade-to-teams-on-prem-implement.md)」を参照してください。 組織でSkype for Business Serverを使用している場合は、SkypeとTeamsの間の相互運用性に関する記事「[移行とSkype for Businessとの相互運用性](migration-interop-guidance-for-teams-with-skype.md)」を参照してください。

## <a name="see-also"></a>関連項目

[ダイレクト ルーティングを計画する](direct-routing-plan.md)

[ダイレクト ルーティングを構成する](direct-routing-configure.md)
