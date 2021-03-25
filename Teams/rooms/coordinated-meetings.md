---
title: Microsoft Teams の会議室と Surface Hub で調整された会議を設定する
ms.author: dstrome
author: dstrome
ms.reviewer: rahulmi
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
localization_priority: Normal
description: 1 つのデバイスまたは他のデバイスが会議に参加するときに会議に参加する Teams 会議室デバイスと Surface Hub を構成します。
ms.openlocfilehash: 57dc91e4a7d923e218cd1f8f6f0ce22679d550e3
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117565"
---
# <a name="set-up-coordinated-meetings-with-microsoft-teams-rooms-and-surface-hub"></a>Microsoft Teams の会議室と Surface Hub で調整された会議をセットアップする

会議室に 1 つ以上の Microsoft Teams 会議室デバイスまたは Surface Hub がある場合は、調整された会議を設定できます。 調整された会議では、Teams 会議室デバイスと Surface Hub をセットアップして、1 つのデバイスで会議に参加すると、会議室内の他のデバイスも同じ会議に参加できます。 カメラ、スピーカー、マイクを構成して、参加者に最適なエクスペリエンスを提供するカメラ、スピーカー、マイクを他のユーザーが無効にできます。 これにより、複数のデバイスを会議に追加するときに、参加者が発生する恐ろしいエコーとフィードバック ノイズを回避できます。

調整された会議を設定するには、Teams 会議室デバイスと Surface Hub が会議に参加するように正しく構成されていることを確認する必要があります。 最も重要な点は、各デバイスに独自の Exchange Room メールボックスが必要です。 設定方法については、次の記事を参照してください。

- [Microsoft Teams Rooms をデプロイする](../rooms/rooms-deploy.md)
- [Surface Hub 2S デバイス アカウントを作成する](/surface-hub/surface-hub-2s-account)

Teams 会議室デバイスと Surface Hub が会議を自動的に承諾し、会議に正常に参加できると確認したら、調整された会議を設定できます。

会議室ごとに次の手順を実行する必要があります。 1 つの会議室のデバイスは、他の会議室のデバイスを使用して調整された会議用に設定する必要があります。

## <a name="step-1-plan-your-coordinated-meeting-experience"></a>手順 1: 調整された会議エクスペリエンスを計画する

構成を変更する前に、会議室ごとに何を行うデバイスを決定する必要があります。 つまり、特定の会議室では、アクティブなマイク、カメラ、ホワイトボードを持つデバイスを決定する必要があります。 デバイスの構成方法は、特定の環境によって異なりますが、最初に一般的な推奨事項を次に示します。

- **マイク** Teams の会議室デバイス
- **カメラ** Teams Rooms デバイス (既定ではオン) と Surface Hub (既定ではオフですが、参加者によるオンは許可)
- **ホワイトボード** Surface Hub

> [!IMPORTANT]
> マイクは 1 つのデバイスでのみ有効にしてください。 複数のデバイスで有効にした場合は、オーディオ エコーとフィードバックが発生します。

## <a name="step-2-get-your-devices-upns"></a>手順 2: デバイスの UPN を取得する

会議室で調整された会議エクスペリエンスを設定する場合は、その会議室内の Teams 会議室デバイスと Surface Hub に、どのデバイスを調整する必要かを知る必要があります。 これは、構成に調整する必要があるデバイスのユーザー プリンシパル名 (UPN) を追加することで行われます。 調整された会議用にセットアップする各デバイスの UPN が分からない場合は、Microsoft 365 管理センターを使用して検索できます。 

Microsoft 365 管理センターにアクセスするには、管理者の役割が割り当てられている必要があります。 詳細については、「管理者ロール [について」を参照してください](/microsoft-365/admin/add-users/about-admin-roles)。

Teams 会議室デバイスと Surface Hub の UPN を取得するには、次の操作を行います。

1. Microsoft 365 管理センターにアクセスしてサインインします https://admin.microsoft.com 。
2. [アクティブな **ユーザー]**  >  **に移動します**。
3. Teams Rooms デバイスまたは Surface Hub の名前を [表示名] 列で見つける (ユーザーが多い場合は、[検索] ボックスを使用できます)。
4. [ユーザー名] 列で **UPN** を見つける ([ユーザー名] 列または [ユーザー名] alias@contoso.com alias@contoso.onmicrosoft.com。
5. 調整された会議に参加するデバイスごとに、この操作を繰り返します。

## <a name="step-3-create-a-deployment-worksheet"></a>手順 3: 展開ワークシートを作成する

調整された会議のエクスペリエンスを計画し、デバイスの UPN の一覧を収集した後は、展開ワークシートを作成します。 展開ワークシートを使用すると、すべてのデバイスで設定する構成を視覚化し、選択を検証してエラーを確認できます。

スプレッドシート アプリで、最初の列に次の行を追加します。

| Setting                | 説明      |
|------------------------|-----------------|
| **オーディオの既定値**      | 会議の開始時にマイクがアクティブになるデバイスを決定します。 このフィールドを`true`に設定できるのは 1 つのデバイス (通常は Teams ミーティング デバイス) のみで、残りのデバイスはオーディオのエコーやハウリングを避けるためにこのフィールドを`false`に設定しなければなりません。          |
| **オーディオが有効**      | 会議の参加者がマイクのオンとオフを切り替えるかどうかを決定します。 **オーディオの既定** が`false`に設定されているデバイスでは、参加者が誤ってマイクの電源を入れてしまい、オーディオのエコーやハウリングが発生しないように、この設定を`false`に設定しておく必要があります。<p>オーディオ **の既定値が** 設定されている場合、この設定は無視され、参加者はマイクをミュートまたは `true` ミュート解除できます。          |
| **ビデオの既定**      | 会議の開始時にカメラがアクティブになるデバイスを決定します。 最適な操作性を実現するために、他のすべてのデバイスが`false`に設定されている間は、Teams ミーティング デバイスだけを`true`に設定することをお勧めします。          |
| **ビデオが有効**      | 会議の参加者がカメラのオンとオフを切り替えるかどうかを決定します。 参加者が、Surface Hub ホワイトボードを使用している場合など、イベント参加者が別のデバイスで`true`に設定することができるようにします。 参加者がデバイスでカメラのオンとオフを切り替えることができないようにする場合は、`false`に設定します。<p> ビデオ **の既定値が** 設定されている場合、この設定は無視され、参加者は `true` カメラのオンとオフを切り替えます。         |
| **ホワイトボードの既定** | Teams 会議室デバイスが、会議の参加者の 1 人によって共有されるホワイトボードを表示するかどうかを決定します。 Surface Hub をお持ちで、Surface Hub をお持ちでない場合は、この設定 `false` `true` をお勧めします。 この設定は、Surface Hub には影響しません。 Surface Hubs には、会議の参加者が共有するホワイトボードが常に表示されます。         |
| **ホワイトボードが有効** | 会議の参加者がホワイトボードのオンとオフを切り替えるかどうかを決定します。 参加者がデバイスでホワイトボードのオンとオフを切り替えることができないようにする場合は、`false`に設定します。 <p>Whiteboard **の既定値が** 設定されている場合、この設定は無視され、参加者はホワイトボードのオン `true` とオフを切り替えます。
| **信頼できるアカウント**   | これは、それぞれの Teams ミーティング デバイスまたは Surface Hub 用の UPN をカンマで区切ったリストで、デバイスが会議への参加依頼を承諾するか、または送信する必要があるかを指定します。 |

後続の列で、Teams 会議室の各デバイスと Surface Hub を追加します。 各列に、会議室に必要なエクスペリエンスに対応する値を入力します。 Teams Rooms デバイスが 1 つ、Surface Hub が 1 つある場合の例を次に示します。

- Teams デバイス
  - 会議が始まると **、音声と** ビデオがオンにされます。 参加者 **は、音声** とビデオのオンとオフを切り替えます。
  - 共有ホワイトボードの表示はオフになります。
- Surface Hub
  - 会議の開始 **時に音声** がオフになります。 参加者 **は音声のオン** とオフを切り替えできない。
  - 会議の開始 **時にビデオ** がオフになります。 参加者 **はビデオの** オンとオフを切り替えます。

| Setting                | Teams Room      | Surface Hub      |
|------------------------|-----------------|------------------|
| **オーディオの既定値**      | `true`          | `false`          |
| **オーディオが有効**      | `true`          | `false`          |
| **ビデオの既定**      | `true`          | `false`          |
| **ビデオが有効**      | `true`          | `true`           |
| **ホワイトボードの既定** | `false`         | `false`          |
| **信頼できるアカウント**   | hub@contoso.com | room@contoso.com |

## <a name="step-4-configure-teams-rooms-device"></a>手順 4: Teams 会議室デバイスを構成する

デバイスのタッチ スクリーンを使用して Teams Rooms デバイスで調整された会議をセットアップするか、多くのデバイスをセットアップする必要がある場合に、一中心の場所から設定する必要がある場合は、XML 構成ファイルを使用できます。

前の手順で作成したワークシートを使って、デバイスをセットアップします。

### <a name="use-the-teams-rooms-devices-touch-screen"></a>Teams Rooms デバイスのタッチ スクリーンを使用する

デバイスで調整された会議を設定するには、次の操作を行います。

1. **[... ] を選択します。[その他**  >  **の設定] をクリックします**。
2. 管理者パスワードを入力し、[はい] を **選択します**。
3. [調整 **された会議] を選択します**。
4. [ **オプション] で**、[ **調整された会議] をオン** に _設定します_。
5. ワークシート **のオーディオの** 既定値が [オーディオ] の場合は、[このデバイスのマイクをオンにする] をオンにし、オンにしない場合 `true` はオフ _のままにします_。 
6. ワークシート **でオーディオが** 有効になっている場合は、[このデバイスのマイクをオンにする] の [会議に参加するときにユーザーが有効にする `true` ]**を選択します**。  このデバイスのマイクをオンに設定している場合、このオプションをオフに設定できない。
7. ワークシート **のビデオの** 既定値が [ビデオ] の場合は、[このデバイスのカメラをオンにする] をオンにし、オンにしない場合 `true` はオフ _のままにします_。 
8. ワークシート **でビデオが** 有効になっている場合は、[このデバイスのカメラをオンにする] で [会議に参加するときにユーザーが有効にする `true` ]**を選択します**。  このデバイスのカメラをオンに設定している場合、このオプションをオフ _に設定できない_。
9. ワークシート **の Whiteboard の既定値** がオンの場合は、このデバイスでホワイトボードをオンにし、オンに設定します。オンにしない場合はオフ `true` _のままにします_。  
10. [ **信頼済みデバイス アカウント]** で、ワークシートの [信頼済みアカウント] に一 **覧表示されている各** UPN を入力します。 複数の UPN をコンマで区切ります。
11. **[保存して終了]** を選択します。

[保存して終了 **] を選択** すると、デバイスが再起動し、調整された会議に参加する準備が整います。

### <a name="use-the-teams-rooms-xml-configuration-file"></a>Teams Rooms XML 構成ファイルを使用する

調整された会議は、Teams Rooms デバイスの XML 構成ファイルを `SkypeSettings.xml` 使用して設定できます。 ファイル `SkypeSettings.xml` は静的なファイルではない。 Teams Rooms デバイスが起動すると、名前の `C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState` 付いたファイルがチェックされます `SkypeSettings.xml` 。 ファイルが存在する場合、デバイスはファイルで指定された構成を読み取り、適用します。 構成の適用が完了すると、ファイルは削除されます。 ファイルの詳細については、「XML 構成ファイルを使用 `SkypeSettings.xml` [して本体の設定を管理する」を参照してください](../rooms/xml-config-file.md#manage-console-settings-with-an-xml-configuration-file)。

構成ファイルの調整された会議の設定の構文を次に示します。

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

デバイスで調整された会議を設定するには、次の操作を行います。

1. [コード] や [メモ帳] などのVisual Studio ファイル エディターで、上記の XML を新しいファイルに貼り付けます。

2. 各 XML 要素をスプレッドシートの対応する値 `true` `false` または値に設定します。 たとえば、オーディオの **既定値が [設定** ] `true` の場合 `<Audio default="true">` 。

3. 必ず `TrustedAccounts` UPN のリストに変更してください。

4. 名前を付けてファイルを保存します `SkypeSettings.xml` 。

5. Teams Rooms デバイスのフォルダーにファイルを配置 `C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState` します。 これにはいくつかの方法があります。

    - **ファイルを Teams 会議室デバイスにコピーする** デバイスにファイルをコピーする前に、ファイル共有を有効にしてネットワーク共有を作成する必要があります。 その後、ネットワーク共有に接続し、デバイスにファイルをコピーできます。 詳細については [、「Microsoft Teams Rooms の保守と運用」を参照してください](../rooms/rooms-operations.md)。
    - **グループ ポリシーを使用する** ファイルをデバイスにコピーするグループ ポリシーを作成します。 詳細については、「グループ ポリシーの [概要」を参照してください](/previous-versions/windows/it-pro/windows-server-2012-r2-and-2012/hh831791(v=ws.11))。
    - **Teams 会議室デバイスにファイルをダウンロードする** 管理モードを使用してデバイスにログインし、ネットワーク共有または USB ドライブからデバイスにファイルをコピーできます。 詳細については、「管理モード [に切り替える」を参照してください](../rooms/rooms-operations.md#switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-is-running)。
    
6. デバイスを再起動します。 これには、次の 2 つの方法があります。

    - **リモート PowerShell** リモート PowerShell を使用してデバイスで [シャットダウン] コマンドを実行できます。 詳細については [、「PowerShell を使用したリモート管理」を参照してください](../rooms/rooms-operations.md)。
    - **[再起動 - コンピューターの実行]** ローカル コンピューターでコマンドレットを実行し、再起動するデバイスの `Restart-Computer` コンピューター名を指定できます。 詳細については、「コンピューターの再起動 [」を参照してください](/powershell/module/microsoft.powershell.management/restart-computer?view=powershell-7)。

## <a name="step-5-configure-surface-hub"></a>手順 5: Surface Hub を構成する

Windows 構成デザイナーを使用してプロビジョニング パッケージを作成し、調整会議の設定を Surface Hub に適用できます。 上記で作成した XML ファイルを Windows 構成デザイナーに貼り付け、プロビジョニング パッケージを作成します。

### <a name="create-coordinated-meetings-xml-configuration-file-for-surface-hub"></a>Surface Hub 用に調整された会議 XML 構成ファイルを作成する

Windows 構成デザイナーと Microsoft Intune の両方を使用して、調整された会議の構成を Surface Hub に適用します。 構成は XML を使用して定義されます。 さらに進む前に、適用する XML を作成する必要があります。

調整された会議 XML 構成ファイルの構文を次に示します。

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

Windows 構成デザイナーまたは Microsoft Intune 用の XML を準備するには、次の操作を行います。

1. [コード] や [メモ帳] などのVisual Studio ファイル エディターで、上記の XML を新しいファイルに貼り付けます。

2. 各 XML 要素をスプレッドシートの対応する値 `true` `false` または値に設定します。 たとえば、オーディオの **既定値が [設定** ] `true` の場合 `<Audio default="true">` 。

3. 必ず `TrustedAccounts` UPN のリストに変更してください。

4. Windows 構成デザイナーでは、XML を 1 行に設定する必要があります。 XML が次のように表示されたように、各行間のすべての改行を削除します。

    ```xml
    <SurfaceHubSettings><BluetoothAdvertisementEnabled>true</BluetoothAdvertisementEnabled>...
    ```

5. コンピューターにファイルを保存します。

XML 構成ファイルを作成したら [、「Surface Hub](surface-hub-manage-config.md) で Microsoft Teams 設定を管理する」の手順に従って、それを Surface Hub に適用します。