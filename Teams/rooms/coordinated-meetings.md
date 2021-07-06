---
title: 会議や会議で調整されたMicrosoft Teams ミーティングをSurface Hub
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
description: デバイスTeams ミーティングを構成しSurface Hubデバイスまたは他のデバイスが会議に参加するときに会議に参加する必要があります。
ms.openlocfilehash: b81d6fca5c263bb8ba1dcd07e80167425bd42fc0
ms.sourcegitcommit: 3704577b1424c063fd925a58a6f6d0b3ff2c8148
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/02/2021
ms.locfileid: "53278680"
---
# <a name="set-up-coordinated-meetings-with-microsoft-teams-rooms-and-surface-hub"></a>会議や会議を使って調整Microsoft Teams ミーティング設定Surface Hub

会議室に 1 つ以上Microsoft Teams ミーティングデバイスまたは Surface Hubs がある場合は、調整された会議を設定できます。 調整された会議では、Teams ミーティング デバイスと Surface Hubs を設定して、1 つのデバイスで会議に参加すると、会議室内の他のデバイスも同じ会議に参加できます。 カメラ、スピーカー、マイクを構成して、参加者に最適なエクスペリエンスを提供するカメラを有効にしながら、他のユーザーを無効にすることができます。 これにより、複数のデバイスを会議に追加するときに、恐ろしいエコーとフィードバック ノイズの参加者が発生する可能性が回避されます。

調整された会議を設定するには、Teams ミーティング デバイスと Surface Hubs が会議に参加するように正しく構成されていることを確認する必要があります。 最も重要なのは、各デバイスに専用のメールボックスとExchange必要です。 設定方法については、次の記事を参照してください。

- [Microsoft Teams Rooms をデプロイする](../rooms/rooms-deploy.md)
- [2S Surface Hub アカウントを作成する](/surface-hub/surface-hub-2s-account)

Teams ミーティング デバイスと Surface Hubs が会議を自動的に受け入れ、会議に正常に参加できると確認したら、調整された会議を設定できます。

次の手順は、会議室ごとに個別に完了する必要があります。 1 つの会議室内のデバイスは、他の会議室のデバイスとの調整された会議には設定できません。

## <a name="step-1-plan-your-coordinated-meeting-experience"></a>手順 1: 調整された会議エクスペリエンスを計画する

構成を変更する前に、どのデバイスが各会議室で何を行うのかを決定する必要があります。 つまり、特定の会議室について、アクティブなマイク、カメラ、ホワイトボードを持つデバイスを決定する必要があります。 デバイスの構成方法は特定の環境によって異なりますが、最初に一般的な推奨事項を次に示します。

- **マイク Teams ミーティング** デバイス
- **カメラ** Teams ミーティング (既定ではオン) および Surface Hub (既定ではオフですが、参加者がオンにできます)
- **Whiteboard Surface Hub**

> [!IMPORTANT]
> マイクは 1 つのデバイスでのみ有効にしてください。 複数のデバイスで有効にした場合は、オーディオ エコーとフィードバックが発生します。

## <a name="step-2-get-your-devices-upns"></a>手順 2: デバイスの UPN を取得する

会議室で調整された会議エクスペリエンスを設定する場合は、その会議室内の Teams ミーティング デバイスと Surface Hubs に、どのデバイスを調整する必要かを伝える必要があります。 これは、調整する必要があるデバイスのユーザー プリンシパル名 (UPN) を構成に追加することで行われます。 調整された会議用に設定する各デバイスの UPN が分からない場合は、次のコマンドを使用Microsoft 365 管理センター。 

管理者ロールを割り当て、管理者ロールにアクセスするMicrosoft 365 管理センター。 詳細については、「管理者ロールについて [」を参照してください](/microsoft-365/admin/add-users/about-admin-roles)。

デバイスと Surface Hubs Teams ミーティングの UPN を取得するには、次の操作を行います。

1. にアクセスして、Microsoft 365 管理センターにサインインします https://admin.microsoft.com 。
2. [ユーザー] **[アクティブ**  >  **なユーザー] に移動します**。
3. [表示名] 列でTeams ミーティングまたはSurface Hubの名前を見つける (ユーザーが多い場合は、[検索] ボックスを使用できます)。
4. [ユーザー名] 列で **UPN** を見つける ([ユーザー名] や [alias@contoso.com alias@contoso.onmicrosoft.com)。
5. 調整された会議に参加するデバイスごとに、この操作を繰り返します。

## <a name="step-3-create-a-deployment-worksheet"></a>手順 3: デプロイ ワークシートを作成する

調整された会議エクスペリエンスを計画し、デバイスの UPN の一覧を収集した後は、展開ワークシートを作成すると便利です。 デプロイ ワークシートを使用すると、すべてのデバイスで設定する構成を視覚化し、選択を検証し、エラーをチェックできます。

スプレッドシート アプリで、最初の列に次の行を追加します。

| Setting                | 説明      |
|------------------------|-----------------|
| **オーディオの既定値**      | 会議の開始時にマイクがアクティブになるデバイスを決定します。 このフィールドを`true`に設定できるのは 1 つのデバイス (通常は Teams ミーティング デバイス) のみで、残りのデバイスはオーディオのエコーやハウリングを避けるためにこのフィールドを`false`に設定しなければなりません。          |
| **オーディオが有効**      | 会議の参加者がマイクのオンとオフを切り替えるかどうかを決定します。 **オーディオの既定** が`false`に設定されているデバイスでは、参加者が誤ってマイクの電源を入れてしまい、オーディオのエコーやハウリングが発生しないように、この設定を`false`に設定しておく必要があります。<p>オーディオ **の既定値が に** 設定されている場合、この設定は無視され、参加者はマイクをミュートまたは `true` ミュート解除できます。          |
| **ビデオの既定値**      | 会議の開始時にカメラがアクティブになるデバイスを決定します。 最適な操作性を実現するために、他のすべてのデバイスが`false`に設定されている間は、Teams ミーティング デバイスだけを`true`に設定することをお勧めします。          |
| **ビデオが有効**      | 会議の参加者がカメラのオンとオフを切り替えるかどうかを決定します。 参加者が、Surface Hub ホワイトボードを使用している場合など、イベント参加者が別のデバイスで`true`に設定することができるようにします。 参加者がデバイスでカメラのオンとオフを切り替えることができないようにする場合は、`false`に設定します。<p> [ **ビデオの既定値]** が に設定されている場合、この設定は `true` 無視され、参加者はカメラのオンとオフを切り替えます。         |
| **ホワイトボードの既定値** | 会議の参加者がTeams ミーティング共有するホワイトボードをデバイスに表示するかどうかを決定します。 この値を に設定することをお勧めします (Surface Hubがインストールされている場合)。また、まだない場合は に `false` `true` 設定することをお勧めします。 この設定は、Surface Hubs には影響しません。 Surface Hubs には、会議の参加者が共有するホワイトボードが常に表示されます。         |
| **ホワイトボードが有効** | 会議の参加者がホワイトボードのオンとオフを切り替えるかどうかを決定します。 参加者がデバイスでホワイトボードのオンとオフを切り替えることができないようにする場合は、`false`に設定します。 <p>**Whiteboard の既定値が に** 設定されている場合、この設定は無視され、参加者はホワイトボードのオンとオフ `true` を切り替えます。
| **信頼できるアカウント**   | これは、それぞれの Teams ミーティング デバイスまたは Surface Hub 用の UPN をカンマで区切ったリストで、デバイスが会議への参加依頼を承諾するか、または送信する必要があるかを指定します。 |

以降の列で、デバイスと Surface Hubs Teams ミーティングを追加します。 各列で、会議室に必要なエクスペリエンスに対応する値を入力します。 1 つのデバイスと 1 つのデバイスTeams ミーティング例を次に示Surface Hub。

- Teams デバイス
  - 会議が開始されると、 **音声と** ビデオがオンにされます。 参加者 **は、音声** とビデオのオンとオフを切り替えます。
  - 共有ホワイトボードの表示がオフになっている。
- Surface Hub
  - 会議の開始 **時に音声** がオフになります。 参加者 **は音声のオン** とオフを切り替えできない。
  - 会議が開始 **されると、** ビデオはオフになります。 参加者 **はビデオの** オンとオフを切り替えます。

| Setting                | TeamsRoom      | Surface Hub      |
|------------------------|-----------------|------------------|
| **オーディオの既定値**      | `true`          | `false`          |
| **オーディオが有効**      | `true`          | `false`          |
| **ビデオの既定値**      | `true`          | `false`          |
| **ビデオが有効**      | `true`          | `true`           |
| **ホワイトボードの既定値** | `false`         | `false`          |
| **信頼できるアカウント**   | hub@contoso.com | room@contoso.com |

## <a name="step-4-configure-teams-rooms-device"></a>手順 4: デバイスをTeams ミーティングする

デバイスのタッチ スクリーンを使用して Teams ミーティング デバイスで調整会議を設定するか、多数のデバイスを設定する必要がある場合に中央の場所からセットアップする必要がある場合は、XML 構成ファイルを使用できます。

前の手順で作成したワークシートを使用して、デバイスの設定に役立ちます。

### <a name="use-the-teams-rooms-devices-touch-screen"></a>デバイスのTeams ミーティングを使用する

デバイスで調整された会議を設定するには、次の操作を行います。

1. **[...] を選択します。その**  >  **他設定。**
2. 管理者パスワードを入力し、[はい] を **選択します**。
3. [調整 **された会議] を選択します**。
4. [オプション **] で**、[**調整された会議] を に**_設定します_。
5. ワークシート **の既定の** オーディオが である場合は、[このデバイスのマイクをオンにする] をオンに設定し、それ以外の場合 `true` はオフ _のままにします_。 
6. ワークシート **で [オーディオ]** が有効になっている場合は、[このデバイスのマイクをオンにする] の [会議に参加するときにユーザーが有効 `true` **にする] を選択します**。  [このデバイスのマイクをオンにする] が [オン] に設定されている場合、この **オプション** をオフに設定できない。
7. ワークシート **の既定の** ビデオが である場合は、[このデバイスのカメラをオンにする] をオンに設定し、それ以外 `true` の場合はオフ _のままにします_。 
8. ワークシート **で [ビデオ]** が有効になっている場合は、[このデバイスのカメラをオンにする] の [会議に参加するときにユーザーが有効 `true` **にする] を選択します**。  [このデバイスのカメラをオンにする] が オンに設定されている場合、 **このオプションを** オフ _に設定できない_。
9. ワークシート **の Whiteboard の既定値** が である場合は、[このデバイスのホワイトボードをオンにする] をオンに設定します。それ以外の場合 `true` は、オフ _のままにします_。 
10. [ **信頼済みデバイス アカウント]** で、ワークシートの [信頼済みアカウント] に一覧表示 **されている各** UPN を入力します。 複数の UPN をコンマで区切ります。
11. **[保存して終了]** を選択します。

[保存して **終了] を選択** すると、デバイスが再起動し、調整された会議に参加する準備が整います。

### <a name="use-the-teams-rooms-xml-configuration-file"></a>XML 構成Teams ミーティング使用する

調整された会議は、デバイスの XML Teams ミーティングを使用して `SkypeSettings.xml` 設定できます。 ファイル `SkypeSettings.xml` は静的ファイルではない。 デバイスがTeams ミーティング、という名前の `C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState` ファイルを確認します `SkypeSettings.xml` 。 ファイルが存在する場合、デバイスは ファイルで指定された構成を読み取って適用します。 構成の適用が完了すると、ファイルは削除されます。 ファイルの詳細については `SkypeSettings.xml` 、XML 構成ファイルを使用した [コンソール設定の管理に関するページを参照してください](../rooms/xml-config-file.md#manage-console-settings-with-an-xml-configuration-file)。

構成ファイルの [調整された会議] 設定の構文を次に示します。

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

1. テキスト ファイル エディター (例: Visual Studio Codeファイルメモ帳、上記の XML を新しいファイルに貼り付けます。

2. 各 XML 要素をスプレッドシートの対応する値 `true` または `false` 値に設定します。 たとえば、オーディオの既定値 **が の場合は** `true` 、 を設定します `<Audio default="true">` 。

3. 必ず `TrustedAccounts` UPN の一覧に変更してください。

4. という名前のファイルを保存します `SkypeSettings.xml` 。

5. ファイルをデバイスのフォルダー Teams ミーティングに配置 `C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState` します。 これにはいくつかの方法があります。

    - **ファイルをデバイスにTeams ミーティングする** ファイルをデバイスにコピーする前に、ファイル共有を有効にしてネットワーク共有を作成する必要があります。 その後、ネットワーク共有に接続し、ファイルをデバイスにコピーできます。 詳細については、「メンテナンスと操作[Microsoft Teams ミーティングを参照してください](../rooms/rooms-operations.md)。
    - **グループ ポリシーを使用する** ファイルをデバイスにコピーするグループ ポリシーを作成します。 詳細については、「グループ ポリシーの概要 [」を参照してください](/previous-versions/windows/it-pro/windows-server-2012-r2-and-2012/hh831791(v=ws.11))。
    - **デバイスにファイルをTeams ミーティングする** 管理モードを使用してデバイスにログインし、ネットワーク共有または USB ドライブからデバイスにファイルをコピーできます。 詳細については、「管理モードに [切り替える」を参照してください](../rooms/rooms-operations.md#switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-is-running)。
    
6. デバイスを再起動します。 これには、次の 2 つの方法があります。

    - **リモート PowerShell** リモート PowerShell を使用して、デバイスで [シャットダウン] コマンドを実行できます。 詳細については [、「PowerShell を使用したリモート管理」を参照してください](../rooms/rooms-operations.md)。
    - **Restart-Computer の実行** ローカル コンピューターで コマンドレットを実行し、再起動するデバイスのコンピューター名 `Restart-Computer` を指定できます。 詳細については [、Restart-Computer に関するページを参照してください](/powershell/module/microsoft.powershell.management/restart-computer?view=powershell-7)。

## <a name="step-5-configure-surface-hub"></a>手順 5: 構成Surface Hub

Windows 構成デザイナーを使用すると、調整会議の設定を Surface Hubs に適用するために使用できるプロビジョニング パッケージを作成できます。 上記で作成した XML ファイルを構成デザイナー Windowsに貼り付け、プロビジョニング パッケージを作成します。

### <a name="create-coordinated-meetings-xml-configuration-file-for-surface-hub"></a>会議用の調整された会議 XML 構成ファイルを作成Surface Hub

構成Windows構成デザイナーとMicrosoft Intune、調整された会議の構成を Surface Hubs に適用するために使用されます。 構成は XML を使用して定義されます。 先に進む前に、適用する XML を作成する必要があります。

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

次の手順に従って、構成デザイナーまたは構成Windows XML を準備Microsoft Intune。

1. テキスト ファイル エディター (例: Visual Studio Codeファイルメモ帳、上記の XML を新しいファイルに貼り付けます。

2. 各 XML 要素をスプレッドシートの対応する値 `true` または `false` 値に設定します。 たとえば、オーディオの既定値 **が の場合は** `true` 、 を設定します `<Audio default="true">` 。

3. 必ず `TrustedAccounts` UPN の一覧に変更してください。

4. Windows構成デザイナーでは、XML を 1 行に設定する必要があります。 XML が次のように表示されたように、各行間のすべての改行を削除します。

    ```xml
    <SurfaceHubSettings><BluetoothAdvertisementEnabled>true</BluetoothAdvertisementEnabled>...
    ```

5. ファイルをコンピューターに保存します。

XML 構成ファイルを作成したら、「Microsoft Teams の設定を管理[](surface-hub-manage-config.md)Surface Hub Surface Hubs に適用する」の手順に従います。