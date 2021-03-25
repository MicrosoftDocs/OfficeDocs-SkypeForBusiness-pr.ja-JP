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
f1.keywords:
- NOCSH
localization_priority: Normal
description: Microsoft Intune と Windows 構成デザイナーを使用して Surface Hub で Microsoft Teams の設定を管理する
ms.openlocfilehash: 9c16fa4875febd3c9e0a8457626db5e09bf90545
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117385"
---
# <a name="manage-microsoft-teams-settings-on-surface-hub"></a>Surface Hub で Microsoft Teams の設定を管理する

Windows 構成デザイナーまたは Microsoft Endpoint Manager の Microsoft Intune を使用して、Surface Hub で Microsoft Teams の設定を管理できます。 Teams の設定を変更するには、Windows 構成デザイナーまたは Microsoft Intune の知識が必要です。 これらのオプションの詳細については、次の記事を参照してください。

- [Windows 10 のプロビジョニング パッケージを作成する](/windows/configuration/provisioning-packages/provisioning-create-package)
- [Microsoft Intune デバイス管理とは](/mem/intune/remote-actions/device-management)

Windows 構成デザイナーは、Surface Hub デバイスが少数しかなく、簡単にアクセスできる場合に便利なオプションです。 Surface Hub が多い場合、またはリモートの場所にある場合は、Microsoft Endpoint Manager で Microsoft Intune を使用します (組織に展開されている場合)。 選択した方法に関係なく、Surface Hub で Teams の設定を変更するには、XML 構成ファイルを作成する必要があります。

## <a name="teams-configuration-file-syntax"></a>Teams 構成ファイルの構文

Surface Hub 上の Teams の構成は、XML ファイルを使用して定義されます。 XML ファイルには、Teams の動作を制御するために使用できるすべての設定が含まれている。 Windows 構成デザイナーと Microsoft Intune の両方が同じ XML 構文を使用します。 Teams 構成 XML ファイルの例を次に示します。

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
| なし                    | `<SurfaceHubSettings>`                    |           | Surface Hub の Teams 構成のすべての構成要素が含まれています。                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| `<SurfaceHubSettings>`  | `<BluetoothAdvertisementEnabled>`         |           | Surface Hub が、すべての接続で使用できるとアドバタイズBluetoothします。<br>受け入れ可能な値: `true` , `false`                                                                                                                                                                                                                                                                                                                                                                                         |
| `<SurfaceHubSettings>`  | `<AutoAcceptProximateMeetingInvitations>` |           | Teams が近接ベースの会議を自動的に受け入れるかどうかを決定します。<br>受け入れ可能な値: `true` , `false`                                                                                                                                                                                                                                                                                                                                                                                                     |
| `<SurfaceHubSettings>`  | `<CoordinatedMeetings>`                   |           | 調整された会議のすべての構成要素が含まれます。                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
|                         |                                           | `enabled` | Teams が他のデバイスとの調整された会議に参加するように構成されているかどうかを決定します。<br>受け入れ可能な値: `true` , `false`                                                                                                                                                                                                                                                                                                                                                                                |
| `<CoordinatedMeetings>` | `<TrustedAccounts>`                       |           | これは、それぞれの Teams ミーティング デバイスまたは Surface Hub 用の UPN をカンマで区切ったリストで、デバイスが会議への参加依頼を承諾するか、または送信する必要があるかを指定します。<br>受け入れ可能な値: 文字列                                                                                                                                                                                                                                                                                                                         |
| `<CoordinatedMeetings>` | `<Settings>`                              |           | 調整された会議の構成オーディオとビデオの構成要素を含む                                                                                                                                                                                                                                                                                                                                                                                                                               |
| `<Settings>`            | `<Audio>`                                 |           | Surface Hub 上の Teams のオーディオ構成を制御します。                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
|                         |                                           | `default` | 会議の開始時にマイクがアクティブになるデバイスを決定します。 このフィールドを`true`に設定できるのは 1 つのデバイス (通常は Teams ミーティング デバイス) のみで、残りのデバイスはオーディオのエコーやハウリングを避けるためにこのフィールドを`false`に設定しなければなりません。<br>受け入れ可能な値: `true` , `false`                                                                                                                                                                                                           |
|                         |                                           | `enabled` | 会議の参加者がマイクのオンとオフを切り替えるかどうかを決定します。 **オーディオの既定** が`false`に設定されているデバイスでは、参加者が誤ってマイクの電源を入れてしまい、オーディオのエコーやハウリングが発生しないように、この設定を`false`に設定しておく必要があります。<p>オーディオ **の既定値が** 設定されている場合、この設定は無視され、参加者はマイクをミュートまたは `true` ミュート解除できます。<br>受け入れ可能な値: `true` , `false`                                                                               |
| `<Settings>`            | `<Video>`                                 |           | Surface Hub 上の Teams のビデオ構成を制御します。                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
|                         |                                           | `default` | 会議の開始時にカメラがアクティブになるデバイスを決定します。 最適な操作性を実現するために、他のすべてのデバイスが`false`に設定されている間は、Teams ミーティング デバイスだけを`true`に設定することをお勧めします。<br>受け入れ可能な値: `true` , `false`                                                                                                                                                                                                                                                                  |
|                         |                                           | `enabled` | 会議の参加者がカメラのオンとオフを切り替えるかどうかを決定します。 参加者が、Surface Hub ホワイトボードを使用している場合など、イベント参加者が別のデバイスで`true`に設定することができるようにします。 参加者がデバイスでカメラのオンとオフを切り替えることができないようにする場合は、`false`に設定します。<p> ビデオ **の既定値が** 設定されている場合、この設定は無視され、参加者は `true` カメラのオンとオフを切り替えます。<br>受け入れ可能な値: `true` , `false` |

## <a name="apply-teams-settings-to-surface-hub"></a>Teams の設定を Surface Hub に適用する

Windows 構成デザイナーまたは Microsoft Endpoint Manager の Microsoft Intune を使用して、Surface Hub の Teams 構成設定を適用または更新します。

### <a name="use-windows-configuration-designer"></a>Windows 構成デザイナーを使用する

Windows 構成デザイナーを使用してプロビジョニング パッケージを作成し、Teams の設定を Surface Hub に適用できます。 上記で作成した XML ファイルを Windows 構成デザイナーに貼り付け、プロビジョニング パッケージを作成します。

> [!IMPORTANT]
> プロビジョニング パッケージを使用して Teams 構成を Surface Hub に既に適用し、それを変更する場合は、まず既存のプロビジョニング パッケージを削除する必要があります。 詳細については [、「Windows 構成デザイナーによって作成されたプロビジョニング パッケージを削除する」を参照してください](#remove-a-provisioning-package-created-by-windows-configuration-designer)。

Windows 構成デザイナーでプロビジョニング パッケージを作成するには、次の操作を行います。

1. ローカル コンピューターに Windows ストアから Windows 構成デザイナーをインストールして開く
2. **[Surface Hub デバイスのプロビジョニング] を選び**、詳細 **エディターに切り替える**
3. 次の画面で **、WindowsTeamSettings Teams を展開**  >  **し**、[構成 **] を選択します。**
4. 中央のウィンドウの [ **構成]** の横にあるフィールドに、上記で作成した XML の 1 行を貼り付けます。
5. [エクスポート **プロビジョニング**  >  **パッケージ] を選択する**
6. プロビジョニング パッケージの名前を [名前] に入力し、[次 **へ]** を **選択**  >  **する**
7. プロビジョニング パッケージを保存する場所を指定し、[次へ] を選択 **する**
8. [ **ビルド] を** 選択してプロビジョニング パッケージを作成し、[完了] を **選択します。**

最後に、プロビジョニング パッケージを作成したら、次の操作を行って、プロビジョニング パッケージを Surface Hub に適用します。

1. 上記で作成したプロビジョニング パッケージを USB ドライブに保存する
2. USB ドライブを Surface Hub に挿入する
3. Surface Hub でスタート メニューを開き、[すべてのアプリ] を選び、[設定] を選 **びます。**
4. 管理者のユーザー名とパスワードを入力し、[はい] を選択 **します。**
5. Surface **Hub、デバイス管理****、** プロビジョニングパッケージの追加または削除、パッケージの追加の順に **移動します。**
6. [**パッケージの選択]** で、プロビジョニング パッケージの横にある [追加] を選択し、Surface Hub を再起動します。

### <a name="use-microsoft-intune"></a>Microsoft Intune を使用する

Microsoft Endpoint Management で Microsoft Intune を使用して Surface Hub を管理している場合は、それを使用して Teams の設定を Surface Hub に適用できます。 新しい構成プロファイルを作成し、上記で作成した XML ファイルをそのプロファイルに貼り付けます。

> [!IMPORTANT]
> Microsoft Intune が構成プロファイルを適用するデバイスを特定するには、Surface Hub がデバイス グループに含されている必要があります。 デバイス グループを作成する方法の詳細については、「グループを追加してユーザーとデバイスを整理 [する」を参照してください](/mem/intune/fundamentals/groups-add)。

次の操作を行って、Teams の設定を Surface Hub に適用する構成プロファイルを作成します。

1. Microsoft Endpoint Manager にサインインするには、 https://endpoint.microsoft.com/
2. デバイス構成 **プロファイルに**  >  **移動し、[プロファイル** の作成 **] を選択する**
3. [プラットフォーム **] で** Windows **10 以降を選択する**
4. [プロファイル **] で**[ユーザー設定] **を選** び、[作成] をクリック **します。**
5. [基本 **] タブの** **[名前**] で、構成プロファイルのわかりやすい名前を入力し、[次へ] を選択 **します。**
6. [構成設定 **] タブで**[追加] を選 **び**、
7. [行の **追加] ウィンドウで** 、次の操作を行います。
    1. わかりやすい名前を付け、必要に応じて、追加する Teams 設定の説明を入力します。
    2. **OMA-URI で**、「`./Vendor/MSFT/SurfaceHub/InBoxApps/Teams/Configurations`
    3. [ **データ型] で**[ **文字列] (XML ファイル) を選択します。**
    4. ファイル ブラウザーを開き、上で作成した XML ファイルを選び **、開く**
8. [追加 **] を選** び、[次へ] を **選び、**
9. [割 **り当て] タブ** で、[割り当 **て] が** [選択したグループ **] に設定されている**
10. [**選択したグループ]** で、含めるグループを選択し、Surface Hub が含まれているグループを選択し、[選択] を選択 **します。**
11. [次へ **] を選択** し、[次へ] を **選択する**
12. [レビュー+ **作成] で [** 作成] を **選択する**

## <a name="remove-teams-settings-from-a-surface-hub"></a>Surface Hub から Teams の設定を削除する

Windows 構成デザイナーまたは Microsoft Endpoint Manager の Microsoft Intune を使用して、Surface Hub の Teams 構成設定を削除します。

### <a name="remove-a-provisioning-package-created-by-windows-configuration-designer"></a>Windows 構成デザイナーによって作成されたプロビジョニング パッケージを削除する

Windows 構成デザイナーによって作成されたプロビジョニング パッケージを使用して Teams の設定を Surface Hub に適用した場合は、次の手順に従ってパッケージとその設定を削除します。

1. Surface Hub でスタート メニューを開き、[すべてのアプリ] を選び、[設定] を選 **びます。**
2. 管理者のユーザー名とパスワードを入力し、[はい] を選択 **します。**
3. Surface **Hub の [****デバイス管理] に移動** し、**プロビジョニング パッケージを追加または削除する**
4. 削除するプロビジョニング パッケージの横にある [削除] を選択 **します。**
5. Surface **Hub に移動し** 、 **アプリの機能&する**
6. **Surface Hub 用 Microsoft Teams を見つけて、[** 詳細オプション]**を選択する**
7. [リセット **] を選** び、もう一 **度 [リセット] を選** び、
8. Surface Hub を再起動する

### <a name="remove-settings-applied-by-microsoft-intune"></a>Microsoft Intune によって適用された設定を削除する

Microsoft Endpoint Management で Microsoft Intune を使用して Teams の設定を Surface Hub に適用した場合は、次の手順に従って構成プロファイルとその設定を削除します。

1. Microsoft Endpoint Manager にサインインするには、 https://endpoint.microsoft.com/
2. デバイス構成 **プロファイル**  >  **に移動する**
3. 削除する調整された会議の設定を含む構成プロファイルを選択します。
4. 構成プロファイルの詳細ページで、[削除]**を選び****、[OK] を選び、**

Surface Hub の調整された会議の設定を含む構成プロファイルを削除した後、次の手順に従って、Surface Hub 上の Teams アプリをリセットします。

1. Surface Hub でスタート メニューを開き、[すべてのアプリ] を選び、[設定] を選 **びます。**
2. 管理者のユーザー名とパスワードを入力し、[はい] を選択 **します。**
3. Surface **Hub に移動し** 、 **アプリの機能&する**
4. **Surface Hub 用 Microsoft Teams を見つけて、[** 詳細オプション]**を選択する**
5. [リセット **] を選** び、もう一 **度 [リセット] を選** び、
6. Surface Hub を再起動する