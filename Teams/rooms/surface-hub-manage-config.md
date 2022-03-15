---
title: 管理Microsoft Teams構成を管理Surface Hub
ms.author: czawideh
author: cazawideh
ms.reviewer: rahulmi
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: 構成Microsoft Teamsを使用してSurface HubのMicrosoft Intune設定Windows管理する
ms.openlocfilehash: a07751ebf601e665254c1dc6c83eb546592b2e28
ms.sourcegitcommit: a894e9397050e09bfaab02e700e943a3bbeb1302
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/15/2022
ms.locfileid: "63503924"
---
# <a name="manage-microsoft-teams-settings-on-surface-hub"></a>アカウントMicrosoft Teams設定を管理Surface Hub

構成デザイナーまたはMicrosoft Teamsを使用して、Surface HubのWindows設定Microsoft Intune管理Microsoft エンドポイント マネージャー。 構成設定Windows変更を行Microsoft Intune構成デザイナーまたは構成デザイナーの知識Teamsがあります。 これらのオプションの詳細については、次の記事を参照してください。

- [アプリケーションのプロビジョニング パッケージを作成Windows 10](/windows/configuration/provisioning-packages/provisioning-create-package)
- [デバイス管理Microsoft Intuneとは](/mem/intune/remote-actions/device-management)

Windows構成デザイナーは、デバイスの数が少ない場合Surface Hub簡単にアクセスできる場合に便利です。 多数の Surface Hub がある場合、またはリモートの場所にある場合は、組織内にデプロイされている場合は、Microsoft Intune Microsoft エンドポイント マネージャー を使用します。 選択した方法に関係なく、XML 構成ファイルを作成して、TEAMS 設定を変更する必要Surface Hub。

## <a name="teams-configuration-file-syntax"></a>Teams構成ファイルの構文

Teamsの構成はSurface Hub XML ファイルを使用して定義されます。 XML ファイルには、アプリケーションの動作を制御するために使用できるすべての設定Teamsされます。 構成Windowsと構成Microsoft Intune同じ XML 構文を使用します。 次に示すのは、構成 XML Teams例です。

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

次の表では、構成ファイルで使用できるすべての構成設定について説明します。

| 親                  | 要素                                   | 属性 | 説明                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
|-------------------------|-------------------------------------------|-----------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| なし                    | `<SurfaceHubSettings>`                    |           | 1 つの構成で構成Teams構成のすべての構成要素がSurface Hub。                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| `<SurfaceHubSettings>`  | `<BluetoothAdvertisementEnabled>`         |           | 特定の接続Surface Hub使用できるかどうかを通知するかどうかをBluetoothします。<br>使用できる値: `true`、。 `false`                                                                                                                                                                                                                                                                                                                                                                                         |
| `<SurfaceHubSettings>`  | `<AutoAcceptProximateMeetingInvitations>` |           | 近接Teams会議を自動的に受け入れるかどうかを決定します。<br>使用できる値: `true`、。 `false`                                                                                                                                                                                                                                                                                                                                                                                                     |
| `<SurfaceHubSettings>`  | `<CoordinatedMeetings>`                   |           | 調整された会議のすべての構成要素が含まれます。                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
|                         |                                           | `enabled` | 他のデバイスとのTeams会議に参加するように構成されているかどうかを決定します。<br>使用できる値: `true`、。 `false`                                                                                                                                                                                                                                                                                                                                                                                |
| `<CoordinatedMeetings>` | `<TrustedAccounts>`                       |           | これは、それぞれの Teams ミーティング デバイスまたは Surface Hub 用の UPN をカンマで区切ったリストで、デバイスが会議への参加依頼を承諾するか、または送信する必要があるかを指定します。<br>使用できる値: 文字列                                                                                                                                                                                                                                                                                                                         |
| `<CoordinatedMeetings>` | `<Settings>`                              |           | 調整された会議の構成オーディオとビデオの構成要素が含まれています。                                                                                                                                                                                                                                                                                                                                                                                                                               |
| `<Settings>`            | `<Audio>`                                 |           | 1 つのデバイス上のTeamsのオーディオ構成をSurface Hub。                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
|                         |                                           | `default` | 会議の開始時にマイクがアクティブになるデバイスを決定します。 このフィールドを`true`に設定できるのは 1 つのデバイス (通常は Teams ミーティング デバイス) のみで、残りのデバイスはオーディオのエコーやハウリングを避けるためにこのフィールドを`false`に設定しなければなりません。<br>使用できる値: `true`、。 `false`                                                                                                                                                                                                           |
|                         |                                           | `enabled` | 会議の参加者がマイクのオンとオフを切り替えるかどうかを決定します。 **オーディオの既定** が`false`に設定されているデバイスでは、参加者が誤ってマイクの電源を入れてしまい、オーディオのエコーやハウリングが発生しないように、この設定を`false`に設定しておく必要があります。<p>オーディオ **の既定値が に** 設定されている `true`場合、この設定は無視され、参加者はマイクをミュートまたはミュート解除できます。<br>使用できる値: `true`、。 `false`                                                                               |
| `<Settings>`            | `<Video>`                                 |           | ビデオのビデオ構成をTeamsでSurface Hub。                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
|                         |                                           | `default` | 会議の開始時にカメラがアクティブになるデバイスを決定します。 最適な操作性を実現するために、他のすべてのデバイスが`false`に設定されている間は、Teams ミーティング デバイスだけを`true`に設定することをお勧めします。<br>使用できる値: `true`、。 `false`                                                                                                                                                                                                                                                                  |
|                         |                                           | `enabled` | 会議の参加者がカメラのオンとオフを切り替えるかどうかを決定します。 参加者が、Surface Hub ホワイトボードを使用している場合など、イベント参加者が別のデバイスで`true`に設定することができるようにします。 参加者がデバイスでカメラのオンとオフを切り替えることができないようにする場合は、`false`に設定します。<p> [ **ビデオの既定値]** が `true`に設定されている場合、この設定は無視され、参加者はカメラのオンとオフを切り替えます。<br>使用できる値: `true`、。 `false` |

## <a name="apply-teams-settings-to-surface-hub"></a>設定をTeamsに適用Surface Hub

構成デザイナーまたはTeamsを使用して、Surface HubにWindows構成設定をMicrosoft Intuneまたは更新Microsoft エンドポイント マネージャー。

### <a name="use-windows-configuration-designer"></a>構成Windowsを使用する

Windows 構成デザイナーを使用してプロビジョニング パッケージを作成できます。このパッケージを使用して、Surface Hubs にTeams設定を適用できます。 上記で作成した XML ファイルを構成デザイナー Windowsに貼り付け、プロビジョニング パッケージを作成します。

> [!IMPORTANT]
> プロビジョニング パッケージを使用して Surface Hub に Teams 構成を既に適用し、それを変更する場合は、まず既存のプロビジョニング パッケージを削除する必要があります。 詳細については、「構成デザイナーで[作成されたプロビジョニング パッケージを削除するWindows参照してください](#remove-a-provisioning-package-created-by-windows-configuration-designer)。

構成デザイナーでプロビジョニング パッケージを作成するには、次Windowsします。

1. ローカル Windowsストアから Windows 構成デザイナーをインストールして開く
2. [**デバイスをプロビジョニングSurface Hubし、[** 詳細エディター **に切り替える] を選択します。**
3. 次の画面で、[**WindowsTeamSettings]** を展開し > **Teams** 構成] **を選択します。**
4. 中央のウィンドウの **[構成] の** 横にあるフィールドに、上で作成した XML の 1 行を貼り付けます。
5. [**ExportProvisioning** >  **パッケージ] を選択します。**
6. [名前] にプロビジョニング パッケージの名前を指定し **、[次** へ **] を** > **選択します。**
7. プロビジョニング パッケージを保存する場所を指定し、[次へ] を選択 **します。**
8. [ **ビルド]** を選択してプロビジョニング パッケージを作成し、[完了] を **選択します。**

最後に、プロビジョニング パッケージを作成したら、次の手順を実行して、プロビジョニング パッケージをプロビジョニング パッケージに適用Surface Hub。

1. 上記で作成したプロビジョニング パッケージを USB ドライブに保存する
2. USB ドライブをデバイスに挿入Surface Hub
3. アプリでSurface Hubを開きスタート メニューすべての **アプリ] を** 選択し、[アプリ] を **選択設定**
4. 管理者のユーザー名とパスワードを入力し、[はい] を **選択します。**
5. [**Surface Hub管理****]、****プロビジョニング パッケージ** の追加または削除、パッケージの追加の順 **に移動します。**
6. [**パッケージの選択] で**、プロビジョニング パッケージ **の** 横にある [追加] を選択し、アプリを再起動Surface Hub

### <a name="use-microsoft-intune"></a>Microsoft Intune を使用する

Surface Hubs が Microsoft Endpoint Management の Microsoft Intune を使用して管理されている場合は、Surface Hubs にTeams設定を適用できます。 新しい構成プロファイルを作成し、上記で作成した XML ファイルをそのプロファイルに貼り付けます。

> [!IMPORTANT]
> Surface Hubs をデバイス グループに含め、構成プロファイルを適用Microsoft Intuneデバイスを特定できる必要があります。 デバイス グループを作成する方法については、「グループを追加してユーザーとデバイスを整理 [する」を参照してください](/mem/intune/fundamentals/groups-add)。

Surface Hubs に設定を適用する構成プロファイルTeamsを作成するには、次の操作を行います。

1. にアクセスしてMicrosoft エンドポイント マネージャーにサインインします。https://endpoint.microsoft.com/
2. [デバイス **]構成** > **プロファイルに移動し、[プロファイル** の作成] **を選択します。**
3. [**プラットフォーム] で**、[Windows 10 **] を選択します。**
4. [プロファイル **] で** [カスタム] **を選択** し、[作成] を **クリックします。**
5. [基本 **] タブの** [名前 **] で**、構成プロファイルのわかりやすい名前を指定し、[次へ] を選択 **します。**
6. [構成設定 **] タブで** 、[追加] を **選択します。**
7. [行 **の追加] ウィンドウ** で、次の操作を行います。
    1. わかりやすい名前を指定し、必要に応じて、追加するTeamsの説明を入力します。
    2. **[OMA-URI] に「」** と入力します。`./Vendor/MSFT/SurfaceHub/InBoxApps/Teams/Configurations`
    3. [データ **型] で**、[ **文字列 (XML ファイル) ] を選択します。**
    4. ファイル ブラウザーを開き、上記で作成した XML ファイルを選択して、[開く] を **選択します。**
8. [追加 **] を選択** し、[次へ] を **選択します。**
9. [割り **当て] タブ** で、[割り当て **] が** [選択したグループ **] に設定されている**
10. [**選択したグループ] で**、[含めるグループの選択] を選択し、Surface Hubs を含むグループを選択し、[選択] を選択 **します。** 
11. [次へ **] を選択** し、[次 **へ] を選択します**
12. [確認と **作成] で [作成**] を **選択します。**

## <a name="remove-teams-settings-from-a-surface-hub"></a>アプリTeams設定を削除Surface Hub

Teams 構成デザイナーまたは Surface Hub を使用して、Windowsの構成設定Microsoft Intune削除Microsoft エンドポイント マネージャー。

### <a name="remove-a-provisioning-package-created-by-windows-configuration-designer"></a>構成デザイナーで作成されたプロビジョニング パッケージWindows削除する

Windows 構成デザイナーによって作成されたプロビジョニング パッケージを使用して Surface Hub に設定を適用した場合は、次の手順に従ってパッケージとその設定を削除します。 Teams

1. アプリでSurface Hubを開きスタート メニューすべての **アプリ] を** 選択し、[アプリ] を **選択設定**
2. 管理者のユーザー名とパスワードを入力し、[はい] を **選択します。**
3. [**Surface Hub 管理**] **に移動** し、[プロビジョニング パッケージの **追加または削除] を選択します。**
4. 削除するプロビジョニング パッケージの横にある [削除] を選択 **します。**
5. [アプリ] **Surface Hub**、[**アプリ] の順に&します。**
6. [詳細 **Microsoft TeamsをSurface Hub** し、[詳細オプション] **を選択します。**
7. [リセット **] を** 選択し、もう一 **度 [リセット] を** 選択します。
8. アカウントを再起動Surface Hub

### <a name="remove-settings-applied-by-microsoft-intune"></a>ユーザーが適用した設定を削除Microsoft Intune

Microsoft Endpoint Management Teams Surface Hub を使用して Microsoft Intune に設定を適用した場合は、次の手順に従って構成プロファイルとその設定を削除します。

1. にアクセスしてMicrosoft エンドポイント マネージャーにサインインします。https://endpoint.microsoft.com/
2. **[デバイス]構成** > **プロファイルに移動します。**
3. 削除する調整された会議の設定を含む構成プロファイルを選択します。
4. 構成プロファイルの詳細ページで、[削除] を選択 **し** 、[OK] を **選択します。**

Surface Hub の調整された会議の設定を含む構成プロファイルを削除した後、次の手順に従って、Teams アプリを Surface Hub。

1. アプリでSurface Hubを開きスタート メニューすべての **アプリ] を** 選択し、[アプリ] を **選択設定**
2. 管理者のユーザー名とパスワードを入力し、[はい] を **選択します。**
3. [アプリ] **Surface Hub**、[**アプリ] の順に&します。**
4. [詳細 **Microsoft TeamsをSurface Hub** し、[詳細オプション] **を選択します。**
5. [リセット **] を** 選択し、もう一 **度 [リセット] を** 選択します。
6. アカウントを再起動Surface Hub
