---
title: Surface Hub で Microsoft Teams の構成を管理する
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
description: Microsoft Intuneと Windows 構成デザイナーを使用して Surface Hub で Microsoft Teams の設定を管理する
ms.openlocfilehash: 6e99922ebb7bb30db1b5e94fd1a4d30b8ec653b8
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2022
ms.locfileid: "67272212"
---
# <a name="manage-microsoft-teams-settings-on-surface-hub"></a>Surface Hub で Microsoft Teams の設定を管理する

Windows 構成デザイナーまたは Microsoft エンドポイント マネージャーのMicrosoft Intuneを使用して、Surface Hub で Microsoft Teams の設定を管理できます。 Teams の設定を変更するには、Windows 構成デザイナーまたはMicrosoft Intuneに関する知識が必要です。 これらのオプションの詳細については、次の記事を参照してください。

- [Windows 10用のプロビジョニング パッケージを作成する](/windows/configuration/provisioning-packages/provisioning-create-package)
- [デバイス管理Microsoft Intuneとは何ですか?](/mem/intune/remote-actions/device-management)

Windows 構成デザイナーは、Surface Hub デバイスが少数しかなく、簡単にアクセスできる場合に適したオプションです。 Surface Hub が多数ある場合、またはリモートの場所にいる場合は、組織に展開されている場合は、Microsoft エンドポイント マネージャーのMicrosoft Intuneを使用します。 選択した方法に関係なく、Surface Hub の Teams 設定を変更するには、XML 構成ファイルを作成する必要があります。

## <a name="teams-configuration-file-syntax"></a>Teams 構成ファイルの構文

Surface Hub の Teams 構成は、XML ファイルを使用して定義されます。 XML ファイルには、Teams の動作を制御するために使用できるすべての設定が含まれています。 Windows 構成デザイナーとMicrosoft Intuneの両方で同じ XML 構文を使用します。 Teams 構成 XML ファイルの例を次に示します。

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
| なし                    | `<SurfaceHubSettings>`                    |           | Surface Hub 上の Teams 構成のすべての構成要素が含まれます。                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| `<SurfaceHubSettings>`  | `<BluetoothAdvertisementEnabled>`         |           | Surface Hub が Bluetooth 接続で使用できることをアドバタイズするかどうかを決定します。<br>受け入れられる値: `true`, `false`                                                                                                                                                                                                                                                                                                                                                                                         |
| `<SurfaceHubSettings>`  | `<AutoAcceptProximateMeetingInvitations>` |           | Teams が近接通信ベースの会議を自動的に受け入れるかどうかを決定します。<br>受け入れられる値: `true`, `false`                                                                                                                                                                                                                                                                                                                                                                                                     |
| `<SurfaceHubSettings>`  | `<CoordinatedMeetings>`                   |           | 座標会議のすべての構成要素を含みます。                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
|                         |                                           | `enabled` | Teams が他のデバイスとの調整された会議に参加するように構成されているかどうかを決定します。<br>受け入れられる値: `true`, `false`                                                                                                                                                                                                                                                                                                                                                                                |
| `<CoordinatedMeetings>` | `<TrustedAccounts>`                       |           | これは、それぞれの Teams ミーティング デバイスまたは Surface Hub 用の UPN をカンマで区切ったリストで、デバイスが会議への参加依頼を承諾するか、または送信する必要があるかを指定します。<br>受け入れられる値: 文字列                                                                                                                                                                                                                                                                                                                         |
| `<CoordinatedMeetings>` | `<Settings>`                              |           | 座標会議の構成オーディオとビデオの構成要素が含まれています                                                                                                                                                                                                                                                                                                                                                                                                                               |
| `<Settings>`            | `<Audio>`                                 |           | Surface Hub 上の Teams のオーディオ構成を制御します。                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
|                         |                                           | `default` | 会議の開始時にマイクをアクティブにするデバイスを決定します。 このフィールドを`true`に設定できるのは 1 つのデバイス (通常は Teams ミーティング デバイス) のみで、残りのデバイスはオーディオのエコーやハウリングを避けるためにこのフィールドを`false`に設定しなければなりません。<br>受け入れられる値: `true`, `false`                                                                                                                                                                                                           |
|                         |                                           | `enabled` | 会議の参加者がマイクのオンとオフを切り替えることができるかどうかを決定します。 **オーディオの既定** が`false`に設定されているデバイスでは、参加者が誤ってマイクの電源を入れてしまい、オーディオのエコーやハウリングが発生しないように、この設定を`false`に設定しておく必要があります。<p>**オーディオの既定値** が設定`true`されている場合、この設定は無視され、参加者はマイクをミュートまたはミュート解除できます。<br>受け入れられる値: `true`, `false`                                                                               |
| `<Settings>`            | `<Video>`                                 |           | Surface Hub 上の Teams のビデオ構成を制御します。                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
|                         |                                           | `default` | 会議の開始時にカメラをアクティブにするデバイスを決定します。 最適な操作性を実現するために、他のすべてのデバイスが`false`に設定されている間は、Teams ミーティング デバイスだけを`true`に設定することをお勧めします。<br>受け入れられる値: `true`, `false`                                                                                                                                                                                                                                                                  |
|                         |                                           | `enabled` | 会議の参加者がカメラのオンとオフを切り替えることができるかどうかを決定します。 参加者が、Surface Hub ホワイトボードを使用している場合など、イベント参加者が別のデバイスで`true`に設定することができるようにします。 参加者がデバイスでカメラのオンとオフを切り替えることができないようにする場合は、`false`に設定します。<p> **ビデオの既定値** が設定`true`されている場合、この設定は無視され、参加者はカメラのオンとオフを切り替えることができます。<br>受け入れられる値: `true`, `false` |

## <a name="apply-teams-settings-to-surface-hub"></a>Surface Hub に Teams 設定を適用する

Windows 構成デザイナーまたは Microsoft エンドポイント マネージャーのMicrosoft Intuneを使用して、Surface Hub の Teams 構成設定を適用または更新します。

### <a name="use-windows-configuration-designer"></a>Windows 構成デザイナーを使用する

Windows 構成デザイナーを使用して、Surface Hubs に Teams 設定を適用するために使用できるプロビジョニング パッケージを作成できます。 上で作成した XML ファイルを Windows 構成デザイナーに貼り付けて、プロビジョニング パッケージを作成します。

> [!IMPORTANT]
> プロビジョニング パッケージを使用して Surface Hub に Teams 構成を既に適用していて、それを変更する場合は、最初に既存のプロビジョニング パッケージを削除する必要があります。 詳細については、「 [Windows 構成デザイナーによって作成されたプロビジョニング パッケージを削除する」を参照](#remove-a-provisioning-package-created-by-windows-configuration-designer)してください。

Windows 構成デザイナーでプロビジョニング パッケージを作成するには、次の手順に従います。

1. ローカル コンピューターに Windows ストアから Windows 構成デザイナーをインストールして開く
2. **[Surface Hub デバイスのプロビジョニング**] を選択し、[**詳細エディターに切り替える] を選択します。**
3. 次の画面で、**WindowsTeamSettings** > **Teams** を展開し、[**構成]** を選択します。
4. 中央のウィンドウの **[構成]** の横にあるフィールドに、上で作成した XML の 1 行を貼り付けます。
5. **[プロビジョニング パッケージ****のエクスポート]** を選択する > 
6. [名前] にプロビジョニング パッケージの名前を **指定** し、[**次へ** > ] を選択します。
7. プロビジョニング パッケージを保存する場所を指定し、[**次へ**] を選択します。
8. **[ビルド]** を選択してプロビジョニング パッケージを作成し、[**完了] を選択します**。

最後に、プロビジョニング パッケージを作成したら、次の手順に従ってプロビジョニング パッケージを Surface Hub に適用します。

1. 上記で作成したプロビジョニング パッケージを USB ドライブに保存する
2. Surface Hub に USB ドライブを挿入する
3. Surface Hub で、[スタート] メニューを開き、[**すべてのアプリ**] を選択し、[**設定]** を選択します。
4. 管理者のユーザー名とパスワードを指定し、[**はい**] を選択します
5. **Surface Hub**、**デバイス管理**、**プロビジョニング パッケージの追加または削除、およびパッケージ****の追加に** 移動します。
6. [ **パッケージの選択]** で、プロビジョニング パッケージの横にある **[追加]** を選択し、Surface Hub を再起動します。

### <a name="use-microsoft-intune"></a>Microsoft Intuneを使用する

Surface Hubs が Microsoft Endpoint Management のMicrosoft Intuneを使用して管理されている場合は、それを使用して Teams の設定を Surface Hubs に適用できます。 新しい構成プロファイルを作成し、上に作成した XML ファイルをそのプロファイルに貼り付けます。

> [!IMPORTANT]
> 構成プロファイルを適用するデバイスをMicrosoft Intuneが識別できるように、Surface Hubs はデバイス グループ内に存在する必要があります。 デバイス グループを作成する方法については、「 [グループを追加してユーザーとデバイスを整理する](/mem/intune/fundamentals/groups-add)」を参照してください。

Surface Hubs に Teams 設定を適用する構成プロファイルを作成するには、次の操作を行います。

1. Microsoft エンドポイント マネージャーにサインインするには、次のページにアクセスします。https://endpoint.microsoft.com/
2. **デバイス** > 構成プロファイルに移動し **、[プロファイルの** 作成] を選択 **します**。
3. [**プラットフォーム**] で **、Windows 10以降を** 選択します。
4. [**プロファイル]** で [**カスタム**] を選択し、[**作成**] をクリックします。
5. [**基本**] タブの [**名前]** で、構成プロファイルのわかりやすい名前を指定し、[**次へ**] を選択します。
6. [**構成設定**] タブで、[**追加**] を選択します。
7. [ **行の追加]** ウィンドウで、次の操作を行います。
    1. わかりやすい名前を指定し、必要に応じて追加する Teams 設定の説明を入力します。
    2. **OMA-URI** で、次のように入力します。`./Vendor/MSFT/SurfaceHub/InBoxApps/Teams/Configurations`
    3. **データ型** で **、文字列 (XML ファイル)** を選択します。
    4. ファイル ブラウザーを開き、上で作成した XML ファイルを選択して **開く**
8. [**追加]** を選択し、[**次へ**] を選択します。
9. [**割り当て**] タブで、[**割り当て]** が **[選択済みグループ]** に設定されていることを確認します
10. [**選択したグループ**] で、[**含めるグループの選択**] を選択し、Surface Hubs を含むグループを選択して、[**選択**] を選択します。
11. **[次へ**]、[**次へ] の順に** 選択します。
12. **[校閲と作成**] で、[**作成**] を選択します。

## <a name="remove-teams-settings-from-a-surface-hub"></a>Surface Hub から Teams の設定を削除する

Windows 構成デザイナーまたは Microsoft エンドポイント マネージャーのMicrosoft Intuneを使用して Surface Hub の Teams 構成設定を削除します。

### <a name="remove-a-provisioning-package-created-by-windows-configuration-designer"></a>Windows 構成デザイナーによって作成されたプロビジョニング パッケージを削除する

Windows 構成デザイナーによって作成されたプロビジョニング パッケージを使用して Surface Hub に Teams 設定を適用した場合は、次の手順に従ってパッケージとその設定を削除します。

1. Surface Hub で、[スタート] メニューを開き、[**すべてのアプリ**] を選択し、[**設定]** を選択します。
2. 管理者のユーザー名とパスワードを指定し、[**はい**] を選択します
3. **Surface Hub**、**デバイス管理** に移動し、**プロビジョニング パッケージを追加または削除** する
4. 削除するプロビジョニング パッケージの横にある [削除] を選択 **します**。
5. **Surface Hub** と **Apps &機能** に移動する
6. **Surface Hub 用の Microsoft Teams** を検索し、[**詳細オプション**] を選択します。
7. **[リセット]** を選択し、もう一度 **[リセット]** を選択します。
8. Surface Hub を再起動する

### <a name="remove-settings-applied-by-microsoft-intune"></a>Microsoft Intuneによって適用された設定を削除する

Microsoft Endpoint Management のMicrosoft Intuneを使用して Surface Hub に Teams 設定を適用した場合は、次の手順に従って構成プロファイルとその設定を削除します。

1. Microsoft エンドポイント マネージャーにサインインするには、次のページにアクセスします。https://endpoint.microsoft.com/
2. **デバイス** > **構成プロファイル** に移動する
3. 削除する座標会議設定を含む構成プロファイルを選択します
4. 構成プロファイルの詳細ページで[**削除**]、[OK] の順に選択 **します**。

Surface Hub の [会議の調整] 設定を含む構成プロファイルを削除したら、次の手順に従って Surface Hub 上の Teams アプリをリセットします。

1. Surface Hub で、[スタート] メニューを開き、[**すべてのアプリ**] を選択し、[**設定]** を選択します。
2. 管理者のユーザー名とパスワードを指定し、[**はい**] を選択します
3. **Surface Hub** と **Apps &機能** に移動する
4. **Surface Hub 用の Microsoft Teams** を検索し、[**詳細オプション**] を選択します。
5. **[リセット]** を選択し、もう一度 **[リセット]** を選択します。
6. Surface Hub を再起動する
