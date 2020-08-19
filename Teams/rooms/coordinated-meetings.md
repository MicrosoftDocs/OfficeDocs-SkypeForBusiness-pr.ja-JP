---
title: Microsoft Teams のルームと Surface Hub でコーディネートされた会議をセットアップする
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
description: 1つのデバイスまたは他のデバイスが会議に参加したときに、会議に参加するようにチームルームデバイスと Surface Hub を構成します。
ms.openlocfilehash: cfd8bd423d8f7765a973d55e42d64773a06bba32
ms.sourcegitcommit: bd13aecbb25c14e17d1b64343df6d80c90b2aa45
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/19/2020
ms.locfileid: "46803939"
---
# <a name="set-up-coordinated-meetings-with-microsoft-teams-rooms-and-surface-hub"></a>Microsoft Teams のルームと Surface Hub でコーディネートされた会議をセットアップする

会議室に1つ以上の Microsoft Teams ルームデバイスまたは Surface Hub がある場合は、調和のとれた会議を設定することができます。 コーディネートされた会議では、チームルームデバイスと Surface Hub をセットアップして、1つのデバイスで会議に参加するときに、その他のデバイスも同じ会議に参加するようにすることができます。 カメラ、スピーカー、マイクを構成して、参加者に最適なエクスペリエンスを提供するものと、他のユーザーが無効になっている場合に、それらを有効にすることができます。 これにより、会議に複数のデバイスを追加するときに、困難なエコーやフィードバックのノイズを受ける可能性があります。

コーディネートされた会議をセットアップするには、チームルームデバイスと Surface Hub が会議に参加するように既に適切に構成されていることを確認する必要があります。 最も重要なことは、各デバイスに専用の Exchange room メールボックスが必要であることです。 設定方法については、次の記事を参照してください。

- [デプロイの概要](../rooms/rooms-deploy.md)
- [Surface Hub 2S device アカウントを作成する](https://docs.microsoft.com/surface-hub/surface-hub-2s-account)

チームルームデバイスおよび Surface Hub が自動的に会議を承諾して参加できることを確認したら、調和のとれた会議を設定することができます。

会議室ごとに次の手順を完了する必要があります。 1つの会議室のデバイスは、他の会議室のデバイスとの調和した会議用に設定することはできません。

## <a name="step-1-plan-your-coordinated-meeting-experience"></a>手順 1: コーディネートした会議のエクスペリエンスを計画する

構成の変更を行う前に、各会議室で何を実行するかを決める必要があります。 つまり、会議室によっては、どのデバイスでアクティブなマイク、カメラ、ホワイトボードを使用するかを決定する必要があります。 デバイスを構成する方法は、特定の環境によって異なりますが、次の一般的な推奨事項について説明します。

- **マイク** Teams 室のデバイス
- **カメラ** Teams 室のデバイス (既定でオン) と Surface Hub (既定ではオフですが、参加者によって有効にすることができます)
- **ホワイトボード** Surface Hub

> [!IMPORTANT]
> マイクは1台のデバイスでのみ有効にしてください。 複数のデバイスで有効にすると、音声エコーとフィードバックが発生します。

## <a name="step-2-get-your-devices-upns"></a>手順 2: デバイスの Upn を取得する

会議室でコーディネートされた会議の環境を設定する場合は、連携させるデバイスを、チームルームのデバイスと Surface Hub に通知する必要があります。 これは、その構成に合わせて調整する必要があるデバイスのユーザープリンシパル名 (UPN) を追加することによって行われます。 コーディネートされた会議用にセットアップする各デバイスの Upn がわからない場合は、Microsoft 365 管理センターを使って見つけることができます。 

Microsoft 365 管理センターにアクセスするには、管理者の役割が割り当てられている必要があります。 詳細については、「 [管理者ロールについ](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)て」を参照してください。

チームルームデバイスおよび Surface Hub の Upn を取得するには、次の操作を行います。

1. にアクセスして、Microsoft 365 管理センターにサインイン https://admin.microsoft.com します。
2. [**ユーザー**  >  の**アクティブな**ユーザーに移動します。
3. [ **表示名** ] 列で、チームルームデバイスまたは Surface Hub の名前を見つけます (多数のユーザーがいる場合は、 **検索** ボックスを使用できます)。
4. [ **Username** ] 列で UPN を見つけます (alias@contoso.com や alias@contoso.onmicrosoft.com などのようになります)。
5. コーディネートされた会議に参加する各デバイスについて、この手順を繰り返します。

## <a name="step-3-create-a-deployment-worksheet"></a>手順 3: 展開ワークシートを作成する

コーディネートされた会議のエクスペリエンスを計画し、デバイスの Upn の一覧を収集したら、展開ワークシートを作成することをお勧めします。 展開ワークシートを使用すると、すべてのデバイスで設定する構成を視覚化することができ、選択した内容を検証してエラーをチェックすることができます。

スプレッドシートアプリで、最初の列に次の行を追加します。

| Setting                | 説明      |
|------------------------|-----------------|
| **オーディオの既定値**      | 会議の開始時にマイクがアクティブになるデバイスを決定します。 1つのデバイス (通常は Teams 室のデバイス) だけがこのフィールドを設定することができます。このフィールドには、 `true` オーディオのエコーとフィードバックを避けるためにこのフィールドを設定する必要があり `false` ます。          |
| **オーディオ有効**      | 会議の参加者がマイクをオンまたはオフに切り替えることができるかどうかを決定します。 **オーディオの既定**値がに設定されているデバイスでは、 `false` `false` 参加者が誤ってマイクをオンにして、音声のエコーやフィードバックを引き起こすことがないように、この設定を設定しておく必要があります。<p>**Audio default**がに設定されている場合 `true` 、この設定は無視され、参加者はマイクをミュートまたはミュート解除することができます。          |
| **既定のビデオ**      | 会議の開始時にカメラがアクティブになるデバイスを決定します。 最適なエクスペリエンスを実現するには、 `true` 他のすべてのデバイスがに設定されている間、Teams のルームデバイスのみを設定することをお勧めし `false` ます。          |
| **ビデオ対応**      | 会議の参加者がカメラをオンまたはオフに切り替えることができるかどうかを決定します。 この設定は `true` 、イベント参加者がさまざまなビデオの視点 (Surface Hub ホワイトボードを使用している場合など) を共有する他のデバイスで行うことができます。 参加者がデバイスでカメラのオンとオフを切り替えることができないようにするには、をに設定 `false` します。<p> **ビデオの既定値**がに設定されている場合 `true` 、この設定は無視され、参加者はカメラをオンまたはオフにすることができます。         |
| **ホワイトボードの既定値** | 会議の参加者の1人によって共有されたホワイトボードを Teams 室のデバイスに表示するかどうかを決定します。 Surface Hub をお持ちでない場合は、これを設定することをお勧めし `false` `true` ます。 この設定は Surface Hub には影響しません。 Surface Hub には、会議の出席者によって共有されているホワイトボードが常に表示されます。         |
| **ホワイトボード有効** | 会議の参加者がホワイトボードをオンまたはオフに切り替えることができるかどうかを決定します。 参加者がデバイスでホワイトボードのオンとオフを切り替えることができないようにするには、をに設定 `false` します。 <p>**ホワイトボードの既定値**がに設定されている場合 `true` 、この設定は無視され、参加者はホワイトボードのオンとオフを切り替えることができます。
| **信頼済みアカウント**   | これは、デバイスが会議参加要求を受け入れる必要がある、またはどの会議参加要求を送信する必要があるかを、各チームルームデバイスまたは Surface Hub のコンマ区切りリストで示します。 |

後続の列で、各チームルームデバイスと Surface Hub を追加します。 各列に、会議室の目的のエクスペリエンスに対応する値を入力します。 次に、1つの Teams ルームデバイスと1つの Surface Hub の例を示します。

- Teams デバイス
  - 会議を開始すると、音声とビデオが有効 **に** なります。 参加者は、オーディオとビデオのオンとオフを切り替える **ことができ** ます。
  - 共有ホワイトボードの表示はオフになっています。
- Surface Hub
  - 会議を開始すると、音声が **オフ** になります。 参加者は、音声のオンとオフを切り替える **ことはできません** 。
  - 会議の開始時に、ビデオは **オフ** になっています。 参加者は、ビデオのオンとオフを切り替える **ことができ** ます。

| Setting                | Teams 室      | Surface Hub      |
|------------------------|-----------------|------------------|
| **オーディオの既定値**      | `true`          | `false`          |
| **オーディオ有効**      | `true`          | `false`          |
| **既定のビデオ**      | `true`          | `false`          |
| **ビデオ対応**      | `true`          | `true`           |
| **ホワイトボードの既定値** | `false`         | `false`          |
| **信頼済みアカウント**   | hub@contoso.com | room@contoso.com |

## <a name="step-4-configure-teams-rooms-device"></a>手順 4: Teams 室デバイスを構成する

デバイスのタッチスクリーンを使用して、チームルームデバイスでコーディネートされた会議を設定するか、複数のデバイスをセットアップする必要があり、1つの場所から一元管理する場合は、XML 構成ファイルを使用できます。

前の手順で作成したワークシートを使って、デバイスをセットアップします。

### <a name="use-the-teams-rooms-devices-touch-screen"></a>Teams のルームデバイスのタッチスクリーンを使う

デバイスでコーディネートされた会議をセットアップするには、次の操作を行います。

1. [...] を選び**ます。その他**  >  の**設定**。
2. 管理者パスワードを入力して、[ **はい]** を選択します。
3. [ **コーディネート**した会議] を選びます。
4. [ **オプション**] で、[ **調和のとれた会議** ] を _[オン_] に設定します。
5. ワークシートに **オーディオの既定値** が設定されている場合は `true` 、[ **このデバイスのマイク** をオンにする] をオンにします。それ以外の場合は _オフ_にします。
6. ワークシートで**音声が有効になって**いる場合は `true` 、[**このデバイスのマイクをオン**にして**会議に参加するときにユーザーに**許可する] を選択します。 このオプションは、[ **このデバイスのマイク** をオンにする] に設定されている場合はオフにできません。
7. ワークシートの **既定のビデオ** の場合は `true` 、[ **このデバイスのカメラ** をオンにする] をオンにし、それ以外の場合は _オフ_にします。
8. ワークシートで**ビデオが有効になって**いる場合は `true` 、[**このデバイスのカメラをオン**にしている**ときに会議に参加するときにユーザーに**許可する] を選択します。 **このデバイスの [カメラ**] がオンに設定されている場合は、このオプションを_無効にできません。_
9. **ホワイトボードの既定値**がワークシート内にある場合は、[ `true` **このデバイスの whiteboarding**をオンにする]_をオン_にします。それ以外の場合は_オフ_にします。
10. [ **信頼できるデバイスアカウント**] で、ワークシートの **信頼済みアカウント** に一覧表示されている各 UPN を入力します。 複数の Upn はコンマで区切ります。
11. [ **保存して終了**] を選びます。

[ **保存して終了**] を選択すると、デバイスが再起動し、調和のとれた会議に参加することができます。

### <a name="use-the-teams-rooms-xml-configuration-file"></a>Teams の会議の XML 構成ファイルを使用する

コーディネートされた会議は、Teams の部屋のデバイスの XML 構成ファイルを使って設定でき `SkypeSettings.xml` ます。 `SkypeSettings.xml`ファイルは静的ファイルではありません。 Teams のルームデバイスが起動すると、 `C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState` という名前のファイルがチェックインされ `SkypeSettings.xml` ます。 ファイルが存在する場合、デバイスはファイルで指定された構成を読み取り、適用します。 構成の適用が完了すると、ファイルが削除されます。 ファイルの詳細につい `SkypeSettings.xml` ては、「 [XML 構成ファイルを使ってコンソールの設定を管理する](../rooms/xml-config-file.md#manage-console-settings-with-an-xml-configuration-file)」を参照してください。

構成ファイルの調整された会議の設定の構文は、次のとおりです。

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

デバイスでコーディネートされた会議をセットアップするには、次の操作を行います。

1. Visual Studio のコードやメモ帳などのテキストファイルエディターで、上の XML を新しいファイルに貼り付けます。

2. 各 XML 要素を、 `true` スプレッドシートの対応する値または値に設定し `false` ます。 たとえば、Audio の **既定値** がである場合は `true` 、を設定 `<Audio default="true">` します。

3. `TrustedAccounts`Upn のリストに変更してください。

4. ファイルに名前を付けて保存し `SkypeSettings.xml` ます。

5. Teams のルームデバイスのフォルダーにファイルを配置し `C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState` ます。 これにはいくつかの方法があります。

    - **ファイルを Teams 室のデバイスにコピーする** ファイルをデバイスにコピーするには、ファイル共有を有効にしてネットワーク共有を作成する必要があります。 この操作を行うと、ネットワーク共有に接続して、ファイルをデバイスにコピーできるようになります。 詳細については、「 [Microsoft Teams の会議室のメンテナンスと操作](../rooms/rooms-operations.md)」を参照してください。
    - **グループポリシーを使用** するグループポリシーを作成して、ファイルをデバイスにコピーします。 詳細については、「 [グループポリシーの概要](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-r2-and-2012/hh831791(v=ws.11))」を参照してください。
    - **Teams 室のデバイスにファイルをダウンロード** する管理モードを使用してデバイスにログインし、ネットワーク共有または USB ドライブからデバイスにファイルをコピーできます。 詳細については、「 [管理者モードへの切り替え](../rooms/rooms-operations.md#switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-is-running)」を参照してください。
    
6. デバイスを再起動します。 これはいくつかの方法で行うことができます。

    - **リモート PowerShell** リモート PowerShell を使用して、デバイスで Shutdown コマンドを実行できます。 詳細については、「 [PowerShell を使用したリモート管理](../rooms/rooms-operations.md)」を参照してください。
    - **再起動を実行する-コンピューター**`Restart-Computer`ローカルコンピューターでコマンドレットを実行し、再起動するデバイスのコンピューター名を指定できます。 詳細については、「 [コンピューターを再起動](https://docs.microsoft.com/powershell/module/microsoft.powershell.management/restart-computer?view=powershell-7)する」を参照してください。

## <a name="step-5-configure-surface-hub"></a>手順 5: Surface Hub を構成する

Windows 構成デザイナーを使用してプロビジョニングパッケージを作成すると、Surface Hub に会議の調整の設定を適用することができます。 上で作成した XML ファイルを Windows 構成デザイナーに貼り付けて、プロビジョニングパッケージを作成します。

### <a name="create-coordinated-meetings-xml-configuration-file-for-surface-hub"></a>Surface Hub 用のコーディネートした会議の XML 構成ファイルを作成する

Windows 構成デザイナーと Microsoft Intune の両方を使用して、コーディネートされた会議の構成を Surface Hub に適用します。 構成は XML を使って定義されます。 先に進む前に、適用する XML を作成する必要があります。

コーディネートされた会議 XML 構成ファイルの構文を次に示します。

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

次の手順を実行して、Windows 構成デザイナーまたは Microsoft Intune 用の XML を準備します。

1. Visual Studio のコードやメモ帳などのテキストファイルエディターで、上の XML を新しいファイルに貼り付けます。

2. 各 XML 要素を、 `true` スプレッドシートの対応する値または値に設定し `false` ます。 たとえば、Audio の **既定値** がである場合は `true` 、を設定 `<Audio default="true">` します。

3. `TrustedAccounts`Upn のリストに変更してください。

4. Windows 構成デザイナーでは、XML を1行に入力する必要があります。 XML が次のように表示されるように、各行間のすべての改行を削除します。

    ```xml
    <SurfaceHubSettings><BluetoothAdvertisementEnabled>true</BluetoothAdvertisementEnabled>...
    ```

5. コンピューターにファイルを保存します。

XML 構成ファイルを作成したら、「 [Surface hub で Microsoft Teams の設定を管理](surface-hub-manage-config.md) する」の手順を使用して、surface hub にそれを適用します。
