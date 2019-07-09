---
title: 仮想デスクトップ インフラストラクチャ用の Teams
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.date: 04/10/2019
ms.topic: article
ms.service: msteams
ms.reviewer: rafarhi
description: 仮想化されたデスクトップインフラストラクチャ (VDI) 環境で Microsoft Teams を実行する方法について説明します。
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1e88a5fb4e8522a94389e3bad24ddc3da8283a53
ms.sourcegitcommit: 2f12e0d4dc2ef8e848a63bf3a9c63e07e4439cf5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/09/2019
ms.locfileid: "35588144"
---
# <a name="teams-for-virtualized-desktop-infrastructure"></a>仮想デスクトップ インフラストラクチャ用の Teams

この記事では、仮想化された環境で Microsoft Teams を使用する場合の要件と制限について説明します。

## <a name="what-is-vdi"></a>VDI とは

仮想デスクトップインフラストラクチャ (VDI) は、デスクトップオペレーティングシステムと、データセンターの中央サーバー上のアプリケーションをホストする仮想化テクノロジです。 これにより、完全にセキュリティが設定された一元的な中央集中ソースを持つユーザーに、完全にカスタマイズされたデスクトップエクスペリエンスを提供できます。 
 
現時点では、仮想化された環境内の Teams は、専用の永続的仮想化マシン (VM) での共同作業とチャット機能のサポートによって提供されています。 最適なユーザーエクスペリエンスを実現するには、この記事のガイダンスに従ってください。 

## <a name="teams-requirements"></a>Teams の要件

### <a name="set-policies-to-turn-off-calling-and-meeting-functionality-in-teams"></a>チームの呼び出しと会議の機能を無効にするポリシーを設定する

チームの通話と会議のエクスペリエンスは、VDI 環境 (近日公開) に合わせて最適化されていません。 チームの呼び出しと会議の機能を無効にするために、ユーザーレベルのポリシーを設定することをお勧めします。

また、Teams デスクトップアプリまたは web アプリのいずれかを使用して、VDI で完全にチームを実行することもできます。 ただし、ユーザーエクスペリエンスが侵害されないようにポリシーを設定することをお勧めします。  

ポリシーの変更が反映されるまでには、多少時間がかかることがあります。 特定のアカウントの変更がすぐに表示されない場合は、数時間後にもう一度お試しください。

> [!NOTE]
> 仮想デスクトップ環境で使用するためにチームの呼び出しと会議が最適化されている場合は、これらのポリシーを元に戻すことができます。また、ユーザーはチームを通常どおりに使用できるようになります。 

#### <a name="calling"></a>通話

**Csteamのポリシー**コマンドレットを使用して、ユーザーがプライベートおよびグループチャットでの呼び出しと呼び出しのオプションを使用できるかどうかを制御します。 ポリシー設定と推奨値の一覧を次に示します。

|ポリシー名  |説明 |推奨値  |
|---------|---------|---------|
|AllowCalling    |相互運用機能呼び出し機能を制御します。 この機能を有効にすると、Skype for Business ユーザーは Teams ユーザーと1対1の通話を行うことができます。また、その逆も可能です。         |Teams での Skype for Business ユーザーからの通話を防ぐには、False に設定します。          |
|AllowPrivateCalling     | チームクライアントの左側のアプリバーで呼び出し元のアプリを使用できるかどうか、およびプライベートチャットでの通話とビデオ通話のオプションをユーザーに表示するかどうかを制御します         |[いいえ] に設定すると、チームの左側のアプリバーから呼び出し元アプリが削除され、プライベートチャットで通話とビデオ通話のオプションが削除されます。          |

#### <a name="create-and-assign-a-calling-policy"></a>通話ポリシーを作成して割り当てる

1. 管理者として Windows PowerShell セッションを開始します。
2. Skype オンラインコネクタに接続します。

        # Set Office 365 User Name and Password
        $username = “admin email address”
        password = ConvertTo-SecureString "password" -AsPlainText -Force
        $LiveCred = new-object -typename System.Management.Automation.PSCredential -argumentlist $username, $password
        # Connect to Skype Online
        Import-Module SkypeOnlineConnector
        $sfboSession = New-CsOnlineSession -Credential $LiveCred
        Import-PSSession $sfboSession```

3. 通話ポリシーのオプションの一覧を表示します。

       Get-CsTeamsCallingPolicy
 
4. すべての通話ポリシーが無効になっているビルトインポリシーオプションを探します。 次のように表示されます。
   
        Identity                        : Tag:DisallowCalling
        AllowCalling                    : False
        AllowPrivateCalling             : False
        AllowVoicemail                  : False
        AllowCallGroups                 : False
        AllowDelegation                 : False
        AllowUserControl                : False
        AllowCallForwardingToUser       : False
        AllowCallForwardingToPhone      : False
        PreventTollBypass               : False

5. 仮想化された環境で Teams を使用するすべてのユーザーに、DisallowCalling 組み込みポリシーオプションを適用します。

        Grant-CsTeamsCallingPolicy -PolicyName DisallowCalling -Identity “user email id”

Teams の通話ポリシーの詳細については、「 [Set-Csteamのポリシー](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy)」を参照してください。

#### <a name="meetings"></a>会議

**CsTeamsMeetingPolicy**コマンドレットを使用して、ユーザーが作成できる会議の種類、会議中にアクセスできる機能、匿名ユーザーと外部ユーザーが使用できる会議機能を制御します。 ポリシー設定と推奨値の一覧を次に示します。

|ポリシー名 |説明|推奨値                   |
|-------------------|-----------------|-----------------------|
|AllowPrivateMeetingScheduling  | ユーザーがプライベート会議のスケジュールを許可されているかどうかを決定します。| ユーザーがプライベート会議をスケジュールできないようにするには、False に設定します。  |
|Allowchannel会議のスケジュール  | ユーザーがチャネル会議のスケジュールを許可するかどうかを決定します。 | ユーザーがチャネル会議のスケジュールを設定できないようにするには、False に設定します。                       |
|AllowMeetNow |ユーザーが臨時の会議の作成または開始を許可されているかどうかを決定します。              |  ユーザーが臨時の会議を開始できないようにするには、False に設定します。                     |
|ScreenSharingMode | 通話または会議でユーザーが画面を共有できるモードを決定します。 | ユーザーが画面を共有することを禁止するには、[無効」に設定します。                          |
|AllowIPVideo |ユーザーの会議または通話でビデオが有効になっているかどうかを確認します。                  |    ユーザーがビデオを共有することを禁止するには、False に設定します。                                         |
| AllowAnonymousUsersToDialOut | 匿名ユーザーが PSTN 番号へのダイヤルアウトを許可するかどうかを決定します。 | 匿名ユーザーによるダイヤルアウトを禁止するには、False に設定します。                                  |
| AllowAnonymousUsersToStartMeeting | 匿名ユーザーが会議を開始できるかどうかを決定します。     |  ユーザーが会議を開始することを禁止するには False に設定します。                                            |
| AllowOutlookAddIn |ユーザーが Outlook デスクトップクライアントで Teams 会議をスケジュールできるかどうかを決定します。| ユーザーが Outlook デスクトップクライアントで Teams 会議のスケジュールを設定することを禁止するには、False に設定します。|
| AllowParticipantGiveRequestControl|参加者が画面共有の制御を要求できるかどうかを決定します。| ユーザーが会議に参加してコントロールを要求することを禁止するには、False に設定します。    |
| AllowExternalParticipantGiveRequestControl | 外部の参加者が画面共有を要求できるか、制御するかを指定します。| 外部ユーザーによる会議の制御の要求を禁止するには、False に設定します。|
|AllowPowerPointSharing|ユーザーの会議で PowerPoint での共有が許可されているかどうかを決定します。 |ユーザーが会議で PowerPoint ファイルを共有することを禁止するには、False に設定します。  |
|AllowWhiteboard | ユーザーの会議でホワイトボードが許可されているかどうかを決定します。 |   会議でホワイトボードを禁止するには False に設定します。 |
| AllowTranscription |ユーザーの会議で、リアルタイムまたはポスト会議のキャプションと表記を許可するかどうかを決定します。|    会議の議事録とキャプションを禁止するには、False に設定します。  |  
| AllowSharedNotes | ユーザーが共有ノートを取ることを許可されているかどうかを決定します。 | ユーザーが共有のノートを取ることを禁止するには False に設定します。 |
|MediaBitRateKB |会議でのオーディオ/ビデオ/アプリ共有転送のメディアビットレートを決定します  | 推奨される値は、5000 (5 MB) です。 組織のニーズに合わせて変更できます。| 

#### <a name="create-and-assign-a-meeting-policy"></a>会議のポリシーを作成して割り当てる

1. 管理者として Windows PowerShell セッションを開始します。
2. Skype オンラインコネクタに接続します。

        # Set Office 365 User Name and Password
        $username = “admin email address”
        password = ConvertTo-SecureString "password" -AsPlainText -Force
        $LiveCred = new-object -typename System.Management.Automation.PSCredential -argumentlist $username, $password
        # Connect to Skype Online
        Import-Module SkypeOnlineConnector
        $sfboSession = New-CsOnlineSession -Credential $LiveCred
        Import-PSSession $sfboSession```

3. 会議のポリシーオプションの一覧を表示する。

       Get-CsTeamsMeetingPolicy
 
4. すべての会議ポリシーが無効になっている組み込みのポリシーオプションを探します。 次のように表示されます。
   
        Identity                                    : Tag:AllOff
        Description                                 :
        AllowChannelMeetingScheduling               : False
        AllowMeetNow                                : False
        AllowIPVideo                                : False
        AllowAnonymousUsersToDialOut                : False
        AllowAnonymousUsersToStartMeeting           : False
        AllowPrivateMeetingScheduling               : False
        AutoAdmittedUsers                           : False
        AllowCloudRecording                         : False
        AllowOutlookAddIn                           : False
        AllowPowerPointSharing                      : False
        AllowParticipantGiveRequestControl          : False
        AllowExternalParticipantGiveRequestControl  : False
        AllowSharedNotes                            : False
        AllowWhiteboard                             : False
        AllowTranscription                          : False
        MediaBitRateKb                              : False
        ScreenSharingMode                           : False

5. 仮想化された環境で Teams を使用するすべてのユーザーに、[割り当てる] と [ビルトインポリシー] オプションを適用します。 

        Grant-CsTeamsMeetingPolicy -PolicyName AllOff -Identity “user email id”

 Teams 会議ポリシーの詳細については、「 [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy)」を参照してください。

### <a name="virtualization-provider-requirements"></a>仮想化プロバイダーの要件

Teams アプリは、主要な仮想化ソリューションプロバイダーで検証されています。 市場プロバイダーが複数ある場合は、仮想化ソリューションプロバイダーに問い合わせて、最小要件を満たしていることを確認してください。

### <a name="virtual-machine-requirements"></a>仮想マシンの要件

さまざまなワークロードとユーザーニーズが仮想化された環境では、次のような最小の VM 構成が推奨されます。

|パラメーター  |指標  |
|---------|---------|
|vCPU    |  2コア       |
|RAM     |  4 GB      |
|ストレージ     | 8 GB       |

### <a name="virtual-machine-operating-system-requirements"></a>仮想マシンのオペレーティングシステム要件

VM でサポートされているオペレーティングシステムは次のとおりです。

- Windows 10 以降
- Windows Server 2012 R2 以降

## <a name="install-teams-on-vdi"></a>VDI に Teams をインストールする

Teams デスクトップアプリを展開するためのプロセスとツールを次に示します。 

1. 環境に応じて、次のいずれかのリンクを使用して Teams MSI パッケージをダウンロードします。 64ビットのオペレーティングシステムを搭載した VDI VM の64ビットバージョンをお勧めします。

    - [32ビット版](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&download=true&managedInstaller=true)
    - [64ビット版](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&download=true&managedInstaller=true&arch=x64)

2. MSI を VDI VM にインストールするには、次のコマンドを実行します (または完全な更新が必要です)。

        msiexec /i <path_to_msi> /l*v <install_logfile_name> ALLUSER=1

    これにより、チームがプログラムファイルにインストールされます。 この時点で、ゴールデンイメージのセットアップが完了しています。
 
    次の対話型ログオンセッションでは、チームが起動し、資格情報を求められます。 ALLUSER プロパティを使用して VDI に Teams をインストールする場合、Teams の自動起動を無効にすることはできません。 

3. 次のコマンドを実行して、MSI を VDI VM からアンインストールします (または、更新の準備を行います)。

        msiexec /passive /x <path_to_msi> /l*v <uninstall_logfile_name>

    これにより、プログラムファイルから Teams がアンインストールします。

## <a name="known-issues-and-limitations"></a>既知の問題と制限事項

次に示すのは、VDI での Teams の既知の問題と制限です。

- **共有セッションホストの種類の展開**: 共有セッションホストの種類の展開 (たとえば、共有の非永続的な VM 構成) はスコープに含まれません。
- **通話と会議**:

    - 通話と会議のシナリオは VDI 用に最適化されていません。 これらのシナリオでは、パフォーマンスが低下します。 「 [Teams での通話と会議の機能を無効にするポリシーを設定する](#set-policies-to-turn-off-calling-and-meeting-functionality-in-teams)」セクションの説明に従って、ユーザーレベルのポリシーを使用することをお勧めします。  
    - この記事で説明されているポリシーを適用することは、他のポリシーによっては、組織内の他のユーザーに影響を与える可能性がある、通話と会議機能の使用に影響します。 組織内のユーザーが非 VDI クライアントを使用している場合は、ポリシーを適用しないことを選ぶことができます。  

- **他のユーザーが作成した通話と会議への参加**: ポリシーでは、ユーザーが会議を作成することを制限していますが、他のユーザーが会議からダイヤルアウトした場合でも会議に参加できます。 この会議では、ユーザーのビデオ共有機能、ホワイトボードなどの機能は、TeamsMeetingPolicy を使用してこれらの機能を無効にしたかどうかによって異なります。  
- **キャッシュ**されたコンテンツ: Teams が実行されている仮想環境が永続的ではない場合 (各ユーザーセッションの終了時にデータがクリーンアップされた場合)、ユーザーが同じユーザーにアクセスしたかどうかに関係なく、コンテンツの更新によるパフォーマンスの低下が発生する可能性があります。以前のセッションのコンテンツ。
- **クライアントの更新**: vdi 上の teams は、非 vdi teams クライアントと同じように自動的に更新されることはありません。  「 [VDI 上の Teams をインストール](#install-teams-on-vdi)する」セクションで説明されているように、新しい MSI をインストールして VM イメージを更新する必要があります。 最新バージョンに更新するには、現在のバージョンをアンインストールする必要があります。
- **ユーザーエクスペリエンス**: vdi 環境での Teams ユーザーエクスペリエンスは、非 VDI 環境とは異なる場合があります。 違いは、ポリシー設定や環境での機能のサポートが原因である可能性があります。

VDI に関連していない Teams の既知の問題については、「 [Microsoft teams の既知の問題](Known-issues.md)」を参照してください。

## <a name="related-topics"></a>関連トピック

- [MSI を使用して Microsoft Teams をインストールする](msi-deployment.md)
