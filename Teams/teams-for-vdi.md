---
title: 仮想デスクトップ インフラストラクチャのチーム
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.date: 04/10/2019
ms.topic: article
ms.service: msteams
ms.reviewer: ''
description: 仮想デスクトップ インフラストラクチャ (VDI) 環境でマイクロソフトのチームを実行する方法について説明します。
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: c351e0cefc5e4de4ff74a175af4dee064bf96f3f
ms.sourcegitcommit: 946c77b847c1b2c5c43802ecfb0a918fa4f562d9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/15/2019
ms.locfileid: "31869831"
---
# <a name="teams-for-virtualized-desktop-infrastructure"></a>仮想デスクトップ インフラストラクチャのチーム

この資料では、仮想化環境でマイクロソフトのチームを使用するための制限事項と要件について説明します。

## <a name="what-is-vdi"></a>VDI とは何ですか。

仮想デスクトップ インフラストラクチャ (VDI) は、デスクトップ オペレーティング システムおよびデータ センターに集中化されたサーバー上でアプリケーションをホストしている仮想化テクノロジです。 これは、完全にセキュリティで保護された、準拠の一元的なソースを持つユーザーに完全にカスタマイズされたデスクトップのエクスペリエンスを使用できます。 
 
現在、仮想化環境のチームでは専用の永続的な仮想マシン (VM) とのコラボレーションやチャット機能をサポートします。 最適なユーザー エクスペリエンスを確実に、この資料では説明に従います。 

## <a name="teams-requirements"></a>チームの要件

### <a name="set-policies-to-turn-off-calling-and-meeting-functionality-in-teams"></a>呼び出すと、会議のチームの機能を無効にするポリシーを設定します。

チームを呼び出すと、会議の経験はない (準備中)、VDI 環境を最適化されています。 呼び出すと、会議のチームの機能を無効にするユーザー レベルのポリシーを設定することをお勧めします。

チームのデスクトップ アプリケーションまたは web アプリケーションのいずれかを使用して VDI でチームを完全に実行するのには選択することもできます。 ただし、ユーザーの操作性を犠牲にすることを避けるためにポリシーを設定することをお勧めします。  

ポリシーの変更を伝達する (数時間) 時間がかかることができます。 指定したアカウントの変更がすぐに表示されない場合、は、数時間でもう一度してみてください。

> [!NOTE]
> 呼び出すチームおよび会議は、仮想デスクトップ環境で使用するために最適化された、ときに、これらのポリシーを元に戻すし、チームを通常どおりに使用するユーザーを許可します。 

#### <a name="calling"></a>通話

呼び出すと、プライベート通話オプションを使用できるユーザーとグループのチャットをするかどうかは、コントロールに**CSTeamsCallingPolicy**コマンドレットを使用します。 ここでは、ポリシーの設定と推奨される値の一覧です。

|ポリシー名  |説明 |推奨値  |
|---------|---------|---------|
|AllowCalling    |コントロールの相互運用機能を呼び出すことです。 Skype 通話を 1 対 1 のチームのユーザーと、その逆もビジネス ユーザーには、これをオンにできます。         |ビジネス ユーザーがチームでの着陸の Skype からの通話を禁止するのには、False に設定します。          |
|AllowPrivateCalling     | 通話アプリはチームのクライアントの左側にあるバーで、アプリケーションで使用できるかどうかと、ユーザーが通話とビデオのプライベート チャットのオプションを呼び出すを参照してくださいかどうかを制御します。         |チームの左側にあるバーで、アプリケーションから呼び出すアプリケーションを削除するのには、プライベート チャットで通話とビデオ通話のオプションを削除するのには False に設定します。          |

#### <a name="create-and-assign-a-calling-policy"></a>作成し、呼び出し元のポリシーを割り当てる

1. 管理者として Windows PowerShell セッションを開始します。
2. Skype オンライン コネクタに接続します。

        # Set Office 365 User Name and Password
        $username = “admin email address”
        password = ConvertTo-SecureString "password" -AsPlainText -Force
        $LiveCred = new-object -typename System.Management.Automation.PSCredential -argumentlist $username, $password
        # Connect to Skype Online
        Import-Module SkypeOnlineConnector
        $sfboSession = New-CsOnlineSession -Credential $LiveCred
        Import-PSSession $sfboSession```

3. 通話ポリシー オプションの一覧を表示します。

       Get-CsTeamsCallingPolicy
 
4. 呼び出し元のすべてのポリシーが無効になっている組み込みのポリシー オプションを確認します。 次のとおりです。
   
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

5. DisallowCalling の組み込みのポリシー オプションを仮想化環境でチームを使用するすべてのユーザーに適用されます。

        Grant-CsTeamsCallingPolicy -PolicyName DisallowCalling -Identity “user email id”

チームのポリシーの呼び出しの詳細については、[一連の CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy)を参照してください。

#### <a name="meetings"></a>会議

**CsTeamsMeetingPolicy**コマンドレットを使用して、ユーザーが作成した会議、会議中にアクセスできる機能、匿名ユーザーおよび外部ユーザーに利用可能な会議の機能の種類を制御します。 ここでは、ポリシーの設定と推奨される値の一覧です。

|ポリシー名 |説明|推奨値                   |
|-------------------|-----------------|-----------------------|
|AllowPrivateMeetingScheduling  | 秘密の会議をスケジュールするユーザーに許可するかどうかを決定します。| 秘密の会議をスケジュールすることからユーザーを禁止するのには False に設定します。  |
|AllowChannelMeetingScheduling  | チャネルの会議をスケジュールするユーザーに許可するかどうかを決定します。 | チャネルの会議をスケジュールすることからユーザーを禁止する False に設定します。                       |
|AllowMeetNow |ユーザーが作成または、臨時会議を開始できるかどうかを決定します。              |  この設定を false に設定すると、臨時の会議を開始することを禁止します。                     |
|ScreenSharingMode | 通話や会議で画面を共有するユーザーに許可されるモードを決定します。 | 無効に設定すると、画面の共有からユーザーを禁止します。                          |
|AllowIPVideo |ユーザーの会議または呼び出しにビデオが有効になっているかどうかを決定します。                  |    ユーザーが、ビデオを共有することを禁止するのには False に設定します。                                         |
| AllowAnonymousUsersToDialOut | 匿名ユーザーが PSTN 番号にダイアル アウトできるかどうかを決定します。 | 匿名ユーザーがダイヤルアウトするを禁止するのには False に設定します。                                  |
| AllowAnonymousUsersToStartMeeting | 匿名ユーザーが会議を開始できるかどうかを決定します。     |  ユーザーが会議を開始することを禁止するのには False に設定します。                                            |
| AllowOutlookAddIn |ユーザーがチーム会議は、Outlook のデスクトップ クライアントでのスケジュールを設定できるかどうかを決定します。| ユーザーが Outlook のデスクトップ クライアントでのチーム会議をスケジュールすることを禁止するのには False に設定します。|
| AllowParticipantGiveRequestControl|参加者が要求または、画面の共有を制御できるようにするかどうかを決定します。| 与え、その会議内のコントロールを要求するユーザーを禁止するのには False に設定します。    |
| AllowExternalParticipantGiveRequestControl | 外部の参加者が要求または、画面の共有を制御できるようにするかどうかを決定します。| False に設定されてから、外部のユーザーを禁止するミーティングの制御を要求します。|
|AllowPowerPointSharing|ユーザーの会議で PowerPoint の共有を許可するかどうかを決定します。 |ユーザーが会議中の PowerPoint ファイルを共有することを禁止するのには False に設定します。  |
|AllowWhiteboard | ユーザーの会議でホワイト ボードを許可するかどうかを決定します。 |   False に設定すると、会議でホワイト ボードを禁止します。 |
| AllowTranscription |ユーザーの会議で、リアルタイムまたは会議後のキャプションおよびトランスクリプションができるかどうかを決定します。|    議事録と会議内のキャプションを禁止するのには False に設定します。  |  
| AllowSharedNotes | 共有ノートを取ることを許可されているかどうかを決定します。 | False に設定すると、共有のノートを取ることを禁止します。 |
|MediaBitRateKB |オーディオ/ビデオ/アプリケーションの会議での転送を共有するためのメディアのビット レートを決定します。  | 推奨値は、5000 (5 MB) です。 組織のニーズに基づいて変更できます。| 

#### <a name="create-and-assign-a-meeting-policy"></a>作成し、ミーティングのポリシーを割り当てる

1. 管理者として Windows PowerShell セッションを開始します。
2. Skype オンライン コネクタに接続します。

        # Set Office 365 User Name and Password
        $username = “admin email address”
        password = ConvertTo-SecureString "password" -AsPlainText -Force
        $LiveCred = new-object -typename System.Management.Automation.PSCredential -argumentlist $username, $password
        # Connect to Skype Online
        Import-Module SkypeOnlineConnector
        $sfboSession = New-CsOnlineSession -Credential $LiveCred
        Import-PSSession $sfboSession```

3. ミーティングのポリシー オプションの一覧を表示します。

       Get-CsTeamsMeetingPolicy
 
4. 会議のすべてのポリシーが無効になっている組み込みのポリシー オプションを確認します。 次のとおりです。
   
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

5. AllOff の組み込みのポリシー オプションを仮想化環境でチームを使用するすべてのユーザーに適用されます。 

        Grant-CsTeamsMeetingPolicy -PolicyName AllOff -Identity “user email id”

 チームのミーティングのポリシーの詳細については、[一連の CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy)を参照してください。

### <a name="virtualization-provider-requirements"></a>仮想化プロバイダーの要件

チームのアプリケーションは、業界をリードする仮想化ソリューション ・ プロバイダーで検証されました。 複数の市場のプロバイダーでは、最小要件を満たしていることを確認するのには、仮想化ソリューションのプロバイダーを参照してください。

### <a name="virtual-machine-requirements"></a>仮想マシンの要件

多様なワークロードと仮想化された環境でユーザーのニーズと、次に、最低限の VM の構成を推奨します。

|パラメーター  |メジャー  |
|---------|---------|
|vCPU    |  2 コア       |
|RAM     |  4 GB      |
|ストレージ     | 8 GB       |

### <a name="virtual-machine-operating-system-requirements"></a>仮想マシンのオペレーティング システムの要件

VM でサポートされているオペレーティング ・ システムは次のとおりです。

- Windows 10 以降
- Windows Server 2012 R2 以降では

## <a name="install-teams-on-vdi"></a>VDI にチームをインストールします。

ここでは、プロセスとチームのデスクトップ アプリケーションを展開するためのツールです。 

1. 環境によっては、次のリンクのいずれかを使用してチームの MSI パッケージをダウンロードします。 64 ビット バージョンは、64 ビット ・ オペレーティング ・ システムと VDI の VM をお勧めします。

    - [32 ビット版](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&download=true&managedInstaller=true)
    - [64 ビット バージョン](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&download=true&managedInstaller=true&arch=x64)

2. VDI の VM に msi ファイルをインストール (または更新を実行) するには、次のコマンドを実行します。

        msiexec /i <path_to_msi> /l*v <install_logfile_name> ALLUSER=1

    チームのプログラム ファイルをインストールします。 この時点で、ゴールド ・ イメージのセットアップは完了です。
 
    次の対話型ログオン セッションでは、チームを起動し、資格情報を要求します。 チームに VDI の ALLUSER プロパティを使用してインストールする場合は、チームの自動起動を無効にすることがないことに注意してください。 

3. VDI の VM から msi ファイルをアンインストールする (またはそれを更新するための準備) するには、次のコマンドを実行します。

        msiexec /passive /x <path_to_msi> /l*v <uninstall_logfile_name>

    これは、プログラム ファイルからチームをアンインストールします。

## <a name="known-issues-and-limitations"></a>既知の問題と制限事項

次のような問題と VDI のチームに制限します。

- **セッション ホスト型環境の共有**: 共有セッションのホスト型環境 (たとえば、共有非永続的な VM 構成) は、スコープに登録されていません。
- **通話や会議**を表示します。

    - 通話とミーティングの場合は、VDI の最適化されています。 これらのシナリオは、適切に実行されます。 [呼び出すと、会議のチームの機能を無効にするポリシーを設定](#set-policies-to-turn-off-calling-and-meeting-functionality-in-teams)] セクションで説明したようにユーザー レベルのポリシーを使用することをお勧めします。  
    - この資料に記載されているポリシーを適用する他のポリシーによって、組織内の他のユーザーに影響を与える可能性があります、および会議を呼び出す機能を使用する機能に影響します。 組織内のユーザーは、VDI なしのクライアントを使用している場合、ポリシーを適用しないように選択できます。  

- **呼び出しと他のユーザーによって作成されたミーティングへの参加**: ポリシーは、会議の作成からユーザーを制限するに参加できます会議別のユーザーに電話をかけること、会議の場合。 ビデオを共有するユーザーの能力、これらの会議でホワイト ボードの使用およびその他の機能が、TeamsMeetingPolicy を使用してこれらの機能を無効にするかどうかに依存します。  
- **キャッシュされたコンテンツ**: チームで仮想環境の場合、実行が固定されていない (と各ユーザー セッションの最後にデータをクリーンアップ)、ユーザーは、ユーザーが同じにアクセスするかどうかに関係なく、コンテンツの更新に伴うパフォーマンス低下をことがあります前のセッションでのコンテンツです。
- **クライアント用更新プログラム**: VDI のチームは VDI 以外のチームのクライアントがいることと同じように自動的に更新されません。  [VDI のチームのインストール](#install-teams-on-vdi)のセクションで説明したように新しい MSI をインストールすると、VM イメージを更新する必要があります。 新しいバージョンに更新する現在のバージョンをアンインストールする必要があります。
- **ユーザー エクスペリエンス**: VDI 環境で、チームのユーザー エクスペリエンスは、VDI ではない環境とは異なる場合があります。 相違点は、ポリシーの設定が原因であるか、環境内のサポート可能性があります。

チームは既知の VDI に関連しない問題は、[既知の問題に対するマイクロソフトのチーム](Known-issues.md)を参照してください。

## <a name="related-topics"></a>関連トピック

- [MSI を使用して Microsoft Teams をインストールする](msi-deployment.md)