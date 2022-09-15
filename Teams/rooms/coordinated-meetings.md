---
title: Microsoft Teams Roomsと Surface Hub を使用して調整された会議を設定する
ms.author: dstrome
author: dstrome
ms.reviewer: rahulmi
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Rooms
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: 一方のデバイスまたは他のデバイスが会議に参加するときに会議に参加するように、Teams Rooms デバイスと Surface Hub を構成します。
ms.openlocfilehash: 759574015f2138476e0b03ef6fa85b8b105d81ef
ms.sourcegitcommit: 424b14534aa269bb408c97c368102a193b481656
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/14/2022
ms.locfileid: "67706984"
---
# <a name="set-up-coordinated-meetings-with-microsoft-teams-rooms-and-surface-hub"></a>Microsoft Teams Roomsと Surface Hub を使用して座標会議を設定する

会議室に 1 つ以上のMicrosoft Teams Rooms デバイスまたは Surface Hubs がある場合は、座標会議を設定できます。 調整済み会議を使用すると、Teams Rooms デバイスと Surface Hubs を設定して、あるデバイスで会議に参加すると、会議室内の他のデバイスも同じ会議に参加できるようになります。 カメラ、スピーカー、マイクを構成して、参加者に最高のエクスペリエンスを提供するカメラを有効にし、他のユーザーが無効にできます。 これにより、会議に複数のデバイスを追加するときに、参加者が経験できる恐ろしいエコーとフィードバックのノイズを回避できます。

座標会議を設定するには、会議に参加するようにTeams Rooms デバイスと Surface Hubs が既に正しく構成されていることを確認する必要があります。 最も重要なのは、各デバイスに独自の Exchange 会議室メールボックスが必要であることです。 設定方法については、次の記事を参照してください。

- [Microsoft Teams Rooms をデプロイする](../rooms/rooms-deploy.md)
- [Surface Hub 2S デバイス アカウントを作成する](/surface-hub/surface-hub-2s-account)

Teams Rooms デバイスと Surface Hubs が会議を自動的に受け入れて正常に参加できることを確認したら、会議の調整を設定できます。

各会議室に対して、次の手順を個別に実行する必要があります。

## <a name="step-1-plan-your-coordinated-meeting-experience"></a>手順 1: 調整された会議エクスペリエンスを計画する

構成を変更する前に、各会議室で実行するデバイスを決定する必要があります。 つまり、特定の会議室では、アクティブなマイク、カメラ、ホワイトボードを持つデバイスを決定する必要があります。 デバイスの構成方法は、特定の環境によって異なりますが、最初に一般的な推奨事項を次に示します。

- **マイク** Teams Rooms デバイス
- **カメラ** Teams Rooms デバイス (既定ではオン) と Surface Hub (既定ではオフですが、参加者はオンにできます)
- **ホワイト ボード** Surface Hub

> [!IMPORTANT]
> 1 つのデバイスでのみマイクを有効にしてください。 複数のデバイスで有効にすると、オーディオ エコーとフィードバックが発生します。

## <a name="step-2-get-your-devices-upns"></a>手順 2: デバイスの UPN を取得する

会議室で会議の調整エクスペリエンスを設定する場合は、その会議室のTeams Rooms デバイスと Surface Hubs に、調整するデバイスを指示する必要があります。 これは、調整する必要があるデバイスのユーザー プリンシパル名 (UPN) をその構成に追加することによって行われます。 調整済み会議用に設定する各デバイスの UPN がわからない場合は、Microsoft 365 管理センターを使用して見つけることができます。 

Microsoft 365 管理センターにアクセスするには、管理者ロールを割り当てる必要があります。 詳細については、「 [管理者ロールについて](/microsoft-365/admin/add-users/about-admin-roles)」を参照してください。

Teams Rooms デバイスと Surface Hubs の UPN を取得するには、次の操作を行います。

1. アクセスhttps://admin.microsoft.comしてMicrosoft 365 管理センターにサインインします。
2. **[ユーザー****のアクティブユーザー]** >  に移動します。
3. [表示名] 列で、Teams Rooms デバイスまたは Surface Hub の **名前** を見つけます (ユーザーが多い場合は **、[検索**] ボックスを使用できます)。
4. **[ユーザー名]** 列で UPN を見つけます (alias@contoso.com や alias@contoso.onmicrosoft.com のようになります)。
5. 座標会議に参加するデバイスごとに、これを繰り返します。

## <a name="step-3-create-a-deployment-worksheet"></a>手順 3: デプロイ ワークシートを作成する

座標会議エクスペリエンスを計画し、デバイスの UPN の一覧を収集したら、配置ワークシートを作成することをお勧めします。 展開ワークシートは、すべてのデバイスで設定する構成を視覚化するのに役立ちます。これにより、選択内容を検証し、エラーを確認できます。

スプレッドシート アプリで、最初の列に次の行を追加します。

| Setting                | 説明      |
|------------------------|-----------------|
| **オーディオの既定値**      | 会議の開始時にマイクをアクティブにするデバイスを決定します。 このフィールドを`true`に設定できるのは 1 つのデバイス (通常は Teams ミーティング デバイス) のみで、残りのデバイスはオーディオのエコーやハウリングを避けるためにこのフィールドを`false`に設定しなければなりません。          |
| **オーディオが有効になっている**      | 会議の参加者がマイクのオンとオフを切り替えることができるかどうかを決定します。 **オーディオの既定** が`false`に設定されているデバイスでは、参加者が誤ってマイクの電源を入れてしまい、オーディオのエコーやハウリングが発生しないように、この設定を`false`に設定しておく必要があります。<p>**オーディオの既定値** が設定`true`されている場合、この設定は無視され、参加者はマイクをミュートまたはミュート解除できます。          |
| **ビデオの既定値**      | 会議の開始時にカメラをアクティブにするデバイスを決定します。 最適な操作性を実現するために、他のすべてのデバイスが`false`に設定されている間は、Teams ミーティング デバイスだけを`true`に設定することをお勧めします。          |
| **ビデオが有効になっている**      | 会議の参加者がカメラのオンとオフを切り替えることができるかどうかを決定します。 参加者が、Surface Hub ホワイトボードを使用している場合など、イベント参加者が別のデバイスで`true`に設定することができるようにします。 参加者がデバイスでカメラのオンとオフを切り替えることができないようにする場合は、`false`に設定します。<p> **ビデオの既定値** が設定`true`されている場合、この設定は無視され、参加者はカメラのオンとオフを切り替えることができます。         |
| **ホワイトボードの既定値** | Teams Rooms デバイスに、会議参加者の 1 人が共有するホワイトボードを表示するかどうかを決定します。 Surface Hub をお持ちでない場合は、`true`これを`false`設定することをお勧めします。 この設定は Surface Hubs には影響しません。 Surface Hubs には、会議参加者が共有するホワイトボードが常に表示されます。         |
| **ホワイトボードが有効になっている** | 会議の参加者がホワイトボードのオンとオフを切り替えることができるかどうかを決定します。 参加者がデバイスでホワイトボードのオンとオフを切り替えることができないようにする場合は、`false`に設定します。 <p>**ホワイトボードの既定値** が設定`true`されている場合、この設定は無視され、参加者はホワイトボードのオンとオフを切り替えることができます。
| **信頼されたアカウント**   | これは、デバイスが会議参加要求を受け入れる必要があるTeams Roomsデバイスまたは Surface Hub ごとに、または会議参加要求を送信する必要がある UPN のコンマ区切りの一覧です。 |

その後の列で、各Teams Rooms デバイスと Surface Hubs を追加します。 各列に、会議室に必要なエクスペリエンスに対応する値を入力します。 1 つのTeams Rooms デバイスと 1 つの Surface Hub の例を次に示します。

- Teams デバイス
  - 会議が開始されると、オーディオとビデオが **オン** になります。 参加者 **は、** オーディオとビデオのオンとオフを切り替えることができます。
  - 共有ホワイトボードの表示はオフになっています。
- Surface Hub
  - 会議の開始時にオーディオが **オフ** になります。 参加者は、オーディオのオンとオフを切り替 **えることはできません** 。
  - 会議の開始時にビデオが **オフ** になります。 参加者は、ビデオのオンとオフを切り替 **えることができます** 。

| Setting                | Teams Room      | Surface Hub      |
|------------------------|-----------------|------------------|
| **オーディオの既定値**      | `true`          | `false`          |
| **オーディオが有効になっている**      | `true`          | `false`          |
| **ビデオの既定値**      | `true`          | `false`          |
| **ビデオが有効になっている**      | `true`          | `true`           |
| **ホワイトボードの既定値** | `false`         | `false`          |
| **信頼されたアカウント**   | hub@contoso.com | room@contoso.com |

## <a name="step-4-configure-teams-rooms-device"></a>手順 4: デバイスTeams Rooms構成する

デバイスのタッチ 画面を使用してTeams Rooms デバイスで会議の調整を設定するか、多くのデバイスを設定し、中央の場所から行う必要がある場合は、XML 構成ファイルを使用できます。

前の手順で作成したワークシートを使用して、デバイスのセットアップに役立ちます。

### <a name="use-the-teams-rooms-devices-touch-screen"></a>Teams Rooms デバイスのタッチ 画面を使用する

デバイスで会議の調整を設定するには、次の操作を行います。

1. **[..] を選択します。その他の** > **設定**。
2. 管理者パスワードを入力し、[ **はい**] を選択します。
3. [ **座標会議**] を選択します。
4. **[オプション]** で、[**会議の調整**] を _[オン]_ に設定します。
5. ワークシートの **[オーディオ] の既定値** が `true`[ **このデバイスのマイクをオンにする]** をオンに設定します。それ以外の場合は _オフのままにします_。
6. ワークシートで **オーディオが有効になっている** 場合は`true`、[**このデバイスのマイクを有効にする**] で [**会議に参加するときにユーザーを有効にする**] を選択します。 この **デバイスのマイクをオンに** 設定した場合、このオプションをオフにすることはできません。
7. ワークシートの **ビデオの既定値** が [オン] の場合は `true`、[ **このデバイスのカメラをオンにする]** をオンに設定します。それ以外の場合は _オフのままにします_。
8. ワークシートで **ビデオが有効になっている** 場合は`true`、[**このデバイスのカメラを有効にする**] で [**会議に参加するときにユーザーを有効にする**] を選択します。 この **デバイスのカメラをオンに** 設定した場合、このオプションをオフに _することはできません。_
9. ワークシートの **[ホワイトボード**] の既定値が `true`[**このデバイスのホワイトボードをオンにする] をオン** に設定します。それ以外の場合は _オフのままにします_。
10. **[信頼済みデバイス アカウント**] で、ワークシートの **[信頼済みアカウント]** に一覧表示されている各 UPN を入力します。 複数の UPN をコンマで区切ります。
11. 信頼できるデバイスで、近接通信とルーム リモートをオフにします。 
12. **[保存して終了]** を選択します。

**[保存] を選択して終了** すると、デバイスが再起動され、調整された会議に参加できるようになります。

### <a name="use-the-teams-rooms-xml-configuration-file"></a>Teams Rooms XML 構成ファイルを使用する

調整された会議は、Teams Rooms デバイスの `SkypeSettings.xml` XML 構成ファイルを使用して設定できます。 ファイルは `SkypeSettings.xml` 静的ファイルではありません。 Teams Rooms デバイスが起動すると、.. という名前`SkypeSettings.xml`の`C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState`ファイルがチェックインされます。 ファイルが存在する場合、デバイスはファイルで指定された構成を読み取って適用します。 構成の適用が完了すると、ファイルは削除されます。 ファイルの `SkypeSettings.xml` 詳細については、「 [XML 構成ファイルを使用したコンソール設定の管理」を](../rooms/xml-config-file.md#manage-console-settings-with-an-xml-configuration-file)参照してください。

構成ファイルの [座標会議] 設定の構文を次に示します。

```xml
<CoordinatedMeetings enabled="true">
    <Settings>
        <Audio default="true" enabled="true"/>
        <Video default="true" enabled="true"/>
        <Whiteboard default="false" enabled="false"/>
    </Settings>
    <TrustedAccounts>hub@contoso.com</TrustedAccounts>
</CoordinatedMeetings>
```

デバイスで会議の調整を設定するには、次の操作を行います。

1. Visual Studio Code やメモ帳などのテキスト ファイル エディターで、上記の XML を新しいファイルに貼り付けます。

2. 各 XML 要素をスプレッドシート内の対応する `true` 値に `false` 設定します。 たとえば、**オーディオの既定値** が `true`[.`<Audio default="true">`

3. 必ず UPN の一覧に変更 `TrustedAccounts` してください。

4. 名前 `SkypeSettings.xml`を付けてファイルを保存します。

5. Teams Rooms デバイスの`C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState`フォルダーにファイルを配置します。 これを行うには、いくつかの方法があります。

    - **ファイルをTeams Rooms デバイスにコピー** する ファイルをデバイスにコピーするには、ファイル共有を有効にし、ネットワーク共有を作成する必要があります。 その後、ネットワーク共有に接続し、ファイルをデバイスにコピーできます。 詳細については、「[Microsoft Teams Roomsメンテナンスと運用](../rooms/rooms-operations.md)」を参照してください。
    - **グループ ポリシー** グループ ポリシーを作成して、ファイルをデバイスにコピーします。 詳細については、「[グループ ポリシー概要](/previous-versions/windows/it-pro/windows-server-2012-r2-and-2012/hh831791(v=ws.11))」を参照してください。
    - **Teams Rooms デバイスにファイルをダウンロード** する 管理 モードを使用してデバイスにログインし、ネットワーク共有または USB ドライブからデバイスにファイルをコピーできます。 詳細については、「[管理 モードへの切り替え](../rooms/rooms-operations.md#switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-is-running)」を参照してください。
    
6. デバイスを再起動します。 これを行うには、次の方法があります。

    - **リモート PowerShell** デバイスで Shutdown コマンドを実行するには、リモート PowerShell を使用します。 詳細については、「 [PowerShell を使用したリモート管理](../rooms/rooms-operations.md)」を参照してください。
    - **Restart-Computer を実行する** ローカル コンピューターでコマンドレットを `Restart-Computer` 実行し、再起動するデバイスのコンピューター名を指定できます。 詳細については、「 [Restart-Computer](/powershell/module/microsoft.powershell.management/restart-computer?view=powershell-7)」を参照してください。

## <a name="step-5-configure-surface-hub"></a>手順 5: Surface Hub を構成する

Windows 構成デザイナーを使用して、Surface Hubs に会議の調整設定を適用するために使用できるプロビジョニング パッケージを作成できます。 上で作成した XML ファイルを Windows 構成デザイナーに貼り付けて、プロビジョニング パッケージを作成します。

### <a name="create-coordinated-meetings-xml-configuration-file-for-surface-hub"></a>Surface Hub の座標会議 XML 構成ファイルを作成する

Windows 構成デザイナーとMicrosoft Intuneの両方が、Surface Hubs に座標会議の構成を適用するために使用されます。 構成は XML を使用して定義されます。 さらに進む前に、適用される XML を作成する必要があります。

座標会議 XML 構成ファイルの構文を次に示します。

```xml
<SurfaceHubSettings>
    <BluetoothAdvertisementEnabled>true</BluetoothAdvertisementEnabled>
    <AutoAcceptProximateMeetingInvitations>true</AutoAcceptProximateMeetingInvitations>
    <CoordinatedMeetings enabled="true"> 
        <TrustedAccounts>room@contoso.com</TrustedAccounts>
        <Settings> 
            <Audio default="false" enabled="false" />
            <Video default="false" enabled="true" /> 
        </Settings> 
    </CoordinatedMeetings>
</SurfaceHubSettings>
```

Windows 構成デザイナーまたはMicrosoft Intune用の XML を準備するには、次の操作を行います。

1. Visual Studio Code やメモ帳などのテキスト ファイル エディターで、上記の XML を新しいファイルに貼り付けます。

2. 各 XML 要素をスプレッドシート内の対応する `true` 値に `false` 設定します。 たとえば、**オーディオの既定値** が `true`[.`<Audio default="true">`

3. 必ず UPN の一覧に変更 `TrustedAccounts` してください。

4. Windows 構成デザイナーでは、XML を 1 行にする必要があります。 XML が次のように表示されるように、各行間のすべての改行を削除します。

    ```xml
    <SurfaceHubSettings><BluetoothAdvertisementEnabled>true</BluetoothAdvertisementEnabled>...
    ```

5. ファイルをコンピューターに保存します。

XML 構成ファイルを作成したら、「 [Surface Hub で Microsoft Teams の設定を管理](surface-hub-manage-config.md) する」の手順に従って Surface Hubs に適用します。
