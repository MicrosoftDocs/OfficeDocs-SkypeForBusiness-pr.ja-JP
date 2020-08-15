---
title: Surface Hub での Microsoft Teams の構成の管理
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
description: Microsoft Intune と Windows 構成デザイナーを使用した Surface Hub での Microsoft Teams の設定の管理
ms.openlocfilehash: 3e254d7f7afbd918e8279d2dc7b100ebbfdc3daf
ms.sourcegitcommit: 20258b691ffc559b1656fd1e57f67f5c3a9e29e1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/15/2020
ms.locfileid: "46761448"
---
# <a name="manage-microsoft-teams-settings-on-surface-hub"></a>Surface Hub で Microsoft Teams の設定を管理する

Microsoft Teams の設定は、Microsoft Endpoint Manager の Windows 構成デザイナーまたは Microsoft Intune を使って Surface Hub で管理できます。 Teams の設定を変更するには、Windows 構成デザイナーまたは Microsoft Intune に関する知識が必要です。 これらのオプションの詳細については、次の記事を参照してください。

- [Windows 10 用プロビジョニングパッケージを作成する](https://docs.microsoft.com/windows/configuration/provisioning-packages/provisioning-create-package)
- [Microsoft Intune デバイス管理とは](https://docs.microsoft.com/mem/intune/remote-actions/device-management)

Surface Hub デバイスが少数で、簡単にアクセスできる場合は、Windows 構成デザイナーが適しています。 Surface Hub が多すぎる場合、または離れた場所にいる場合は、Microsoft Endpoint Manager で組織が展開されている場合は、Microsoft Intune を使用します。 どちらの方法を選んでも、Surface Hub の Teams の設定を変更するための XML 構成ファイルを作成する必要があります。

## <a name="teams-configuration-file-syntax"></a>Teams 構成ファイルの構文

Surface Hub での Teams の構成は、XML ファイルを使って定義されます。 XML ファイルには、Teams の動作を制御するために使用できるすべての設定が含まれています。 Windows 構成デザイナーと Microsoft Intune はどちらも同じ XML 構文を使用します。 Teams 構成 XML ファイルの例を次に示します。

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

次の表では、構成ファイルで利用できるすべての構成設定について説明します。

| 所属                  | 要素                                   | 属性 | 説明                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
|-------------------------|-------------------------------------------|-----------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| なし                    | `<SurfaceHubSettings>`                    |           | Surface Hub での Teams 構成のすべての構成要素が含まれています。                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| `<SurfaceHubSettings>`  | `<BluetoothAdvertisementEnabled>`         |           | Surface Hub が Bluetooth 接続で利用可能であることをアドバタイズするかどうかを決定します。<br>受け入れられる値: `true` 、 `false`                                                                                                                                                                                                                                                                                                                                                                                         |
| `<SurfaceHubSettings>`  | `<AutoAcceptProximateMeetingInvitations>` |           | チームが近接的ベースの会議を自動的に承諾するかどうかを決定します。<br>受け入れられる値: `true` 、 `false`                                                                                                                                                                                                                                                                                                                                                                                                     |
| `<SurfaceHubSettings>`  | `<CoordinatedMeetings>`                   |           | コーディネートされた会議用のすべての構成要素が含まれています。                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
|                         |                                           | `enabled` | チームが他のデバイスとの連携会議に参加するように構成されているかどうかを決定します。<br>受け入れられる値: `true` 、 `false`                                                                                                                                                                                                                                                                                                                                                                                |
| `<CoordinatedMeetings>` | `<TrustedAccounts>`                       |           | これは、デバイスが会議参加要求を受け入れる必要がある、またはどの会議参加要求を送信する必要があるかを、各チームルームデバイスまたは Surface Hub のコンマ区切りリストで示します。<br>受け入れられる値: 文字列                                                                                                                                                                                                                                                                                                                         |
| `<CoordinatedMeetings>` | `<Settings>`                              |           | コーディネートされた会議用の構成オーディオとビデオの構成要素が含まれています。                                                                                                                                                                                                                                                                                                                                                                                                                               |
| `<Settings>`            | `<Audio>`                                 |           | Surface Hub 上の Teams のオーディオ構成を制御します。                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
|                         |                                           | `default` | 会議の開始時にマイクがアクティブになるデバイスを決定します。 1つのデバイス (通常は Teams 室のデバイス) だけがこのフィールドを設定することができます。このフィールドには、 `true` オーディオのエコーとフィードバックを避けるためにこのフィールドを設定する必要があり `false` ます。<br>受け入れられる値: `true` 、 `false`                                                                                                                                                                                                           |
|                         |                                           | `enabled` | 会議の参加者がマイクをオンまたはオフに切り替えることができるかどうかを決定します。 **オーディオの既定**値がに設定されているデバイスでは、 `false` `false` 参加者が誤ってマイクをオンにして、音声のエコーやフィードバックを引き起こすことがないように、この設定を設定しておく必要があります。<p>**Audio default**がに設定されている場合 `true` 、この設定は無視され、参加者はマイクをミュートまたはミュート解除することができます。<br>受け入れられる値: `true` 、 `false`                                                                               |
| `<Settings>`            | `<Video>`                                 |           | Surface Hub 上の Teams のビデオ構成を制御します。                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
|                         |                                           | `default` | 会議の開始時にカメラがアクティブになるデバイスを決定します。 最適なエクスペリエンスを実現するには、 `true` 他のすべてのデバイスがに設定されている間、Teams のルームデバイスのみを設定することをお勧めし `false` ます。<br>受け入れられる値: `true` 、 `false`                                                                                                                                                                                                                                                                  |
|                         |                                           | `enabled` | 会議の参加者がカメラをオンまたはオフに切り替えることができるかどうかを決定します。 この設定は `true` 、イベント参加者がさまざまなビデオの視点 (Surface Hub ホワイトボードを使用している場合など) を共有する他のデバイスで行うことができます。 参加者がデバイスでカメラのオンとオフを切り替えることができないようにするには、をに設定 `false` します。<p> **ビデオの既定値**がに設定されている場合 `true` 、この設定は無視され、参加者はカメラをオンまたはオフにすることができます。<br>受け入れられる値: `true` 、 `false` |

## <a name="apply-teams-settings-to-surface-hub"></a>Surface Hub にチーム設定を適用する

Microsoft Endpoint Manager で Windows 構成デザイナーまたは Microsoft Intune を使用して、Surface Hub で Teams 構成設定を適用または更新します。

### <a name="use-windows-configuration-designer"></a>Windows 構成デザイナーを使用する

Windows 構成デザイナーを使用してプロビジョニングパッケージを作成し、これを使用してチーム設定を Surface Hub に適用することができます。 上で作成した XML ファイルを Windows 構成デザイナーに貼り付けて、プロビジョニングパッケージを作成します。

> [!IMPORTANT]
> プロビジョニングパッケージを使って既にチーム構成を Surface Hub に適用していて、それを変更する場合は、まず既存のプロビジョニングパッケージを削除する必要があります。 詳細については、「 [Windows 構成デザイナーで作成されたプロビジョニングパッケージを削除する](#remove-a-provisioning-package-created-by-windows-configuration-designer)」を参照してください。

Windows 構成デザイナーでプロビジョニングパッケージを作成するには、次の手順を実行します。

1. ローカルコンピューター上の Windows ストアから Windows 構成デザイナーをインストールして開きます。
2. [ **Surface Hub デバイスのプロビジョニング**] を選択し、[**詳細エディター] に切り替え**ます。
3. 次の画面で、[ **windowsteamsettings**  >  **Teams** ] を展開し、[**構成**] を選択します。
4. 中央のウィンドウの [ **構成** ] の横にあるフィールドに、上の手順で作成した1つの XML 行を貼り付けます。
5. [ **Export**  >  **プロビジョニングパッケージ**のエクスポート] を選ぶ
6. プロビジョニングパッケージの名前を [**名前**] に入力し、[**次**  >  **へ**] を選択します。
7. プロビジョニングパッケージを保存する場所を指定し、[**次へ**] を選択します。
8. [**ビルド**] を選択してプロビジョニングパッケージを作成し、**完了**します。

最後に、プロビジョニングパッケージを作成した後で、次の操作を行って、プロビジョニングパッケージを Surface Hub に適用します。

1. 上の手順で作成したプロビジョニングパッケージを USB ドライブに保存する
2. USB ドライブを Surface Hub に挿入する
3. Surface Hub で、[スタート] メニューを開き、[**すべてのアプリ**] を選択して、[**設定**] を選択します。
4. 管理者のユーザー名とパスワードを入力して、[**はい]** を選択します。
5. **Surface Hub**に移動する、**デバイス管理**、**プロビジョニングパッケージを追加または削除**して、**パッケージを追加**する
6. [ **パッケージの選択**] でプロビジョニングパッケージの横にある [ **追加** ] を選択し、Surface Hub を再起動します。

### <a name="use-microsoft-intune"></a>Microsoft Intune を使用する

Microsoft Endpoint Management で Microsoft Intune を使用して Surface Hub を管理している場合は、それを使って、Surface Hub にチーム設定を適用できます。 新しい構成プロファイルを作成し、上記で作成した XML ファイルをそのプロファイルに貼り付けます。

> [!IMPORTANT]
> Microsoft Intune で構成プロファイルを適用するデバイスを特定できるように、Surface Hub はデバイスグループに含まれている必要があります。 デバイスグループの作成方法については、「 [ユーザーとデバイスを整理するためにグループを追加する](https://docs.microsoft.com/mem/intune/fundamentals/groups-add)」を参照してください。

次の手順に従って構成プロファイルを作成し、Teams の設定を Surface Hub に適用します。

1. アクセスして、Microsoft Endpoint Manager にサインインします。 https://endpoint.microsoft.com/
2. [**デバイス**  >  **構成プロファイル**] に移動し、[**プロファイルの作成**] を選択します。
3. [**プラットフォーム**] で、[ **Windows 10**以降] を選択します。
4. [**プロファイル**] で、[**カスタム**] を選択し、[**作成**] をクリックします。
5. [**基本**] タブの [**名前**] に、構成プロファイルのわかりやすい名前を入力し、[**次へ**] を選択します。
6. [**構成の設定**] タブで、[**追加**] を選びます。
7. [ **行の追加** ] ウィンドウで、次の操作を行います。
    1. わかりやすい名前を入力し、必要に応じて、追加しようとしている Teams の設定の説明を入力します。
    2. **Oma-uri**の場合は、`./Vendor/MSFT/SurfaceHub/InBoxApps/Teams/Configurations`
    3. [**データ型**] で、[**文字列 (XML ファイル)** ] を選択します。
    4. ファイルブラウザーを開き、上で作成した XML ファイルを選択し、[**開く**] をクリックします。
8. [**追加**]、[**次へ**] の順に選択します。
9. [**課題**] タブで、[**割り当て先**] が [**選択したグループ**] に設定されていることを確認します。
10. [**選択したグループ**] で、[**グループの選択**] を選んで、Surface hub を含むグループを選び、[**選択**] を選びます。
11. [**次へ**]、[**次へ**] の選択
12. [**校閲と作成**] で、[**作成**] を選択します。

## <a name="remove-teams-settings-from-a-surface-hub"></a>Surface Hub からチーム設定を削除する

Microsoft Endpoint Manager で Windows 構成デザイナーまたは Microsoft Intune を使用して、Surface Hub の Teams 構成設定を削除します。

### <a name="remove-a-provisioning-package-created-by-windows-configuration-designer"></a>Windows 構成デザイナーによって作成されたプロビジョニングパッケージを削除する

Windows 構成デザイナーによって作成されたプロビジョニングパッケージを使用して、Surface Hub に Teams の設定を適用した場合は、次の手順に従ってパッケージとその設定を削除します。

1. Surface Hub で、[スタート] メニューを開き、[**すべてのアプリ**] を選択して、[**設定**] を選択します。
2. 管理者のユーザー名とパスワードを入力して、[**はい]** を選択します。
3. **Surface Hub**、[**デバイス管理**] の順に移動して、**プロビジョニングパッケージを追加または削除**する
4. 削除するプロビジョニングパッケージの横で、[**削除**] を選択します。
5. **Surface Hub**と**アプリ & 機能**に移動する
6. **Surface Hub 用の Microsoft Teams**を検索して、[**詳細オプション**] を選ぶ
7. [ **リセット**]、[ **リセット] の順に** 選択します。
8. Surface Hub を再起動する

### <a name="remove-settings-applied-by-microsoft-intune"></a>Microsoft Intune によって適用された設定を削除する

Microsoft Intune 管理で Microsoft Intune を使用して Surface Hub に Teams の設定を適用した場合、次の手順を使用して構成プロファイルとその設定を削除します。

1. アクセスして、Microsoft Endpoint Manager にサインインします。 https://endpoint.microsoft.com/
2. **デバイス**  >  **構成プロファイル**に移動する
3. 調整された会議の設定が含まれている構成プロファイルを選択します。
4. [構成プロファイルの詳細] ページで、[**削除**]、[ **OK]** の順に選択します。

Surface Hub のコーディネートされた会議の設定が含まれた構成プロファイルを削除したら、次の手順を使用して Surface Hub の Teams アプリをリセットします。

1. Surface Hub で、[スタート] メニューを開き、[**すべてのアプリ**] を選択して、[**設定**] を選択します。
2. 管理者のユーザー名とパスワードを入力して、[**はい]** を選択します。
3. **Surface Hub**と**アプリ & 機能**に移動する
4. **Surface Hub 用の Microsoft Teams**を検索して、[**詳細オプション**] を選ぶ
5. [ **リセット**]、[ **リセット] の順に** 選択します。
6. Surface Hub を再起動する