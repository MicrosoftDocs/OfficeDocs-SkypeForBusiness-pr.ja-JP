---
title: '[クライアント] メニューのタスクに PowerShell を使用する'
ms.reviewer: ''
ms.author: v-smandalika
author: v-smandalika
manager: dansimp
ms.date: 10/12/2021
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: ''
description: '概要: [クライアントSkype for Business Serverコマンドレット マッピング] にコントロール パネルを表示します。'
ms.openlocfilehash: 1dc0c3a9638af8fdec90fccb633909b9ccf40405
ms.sourcegitcommit: eba9fc680233e9e03773a2942f22afe6247eec41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/08/2021
ms.locfileid: "60824655"
---
# <a name="client"></a>Client

この記事では、従来のコントロール パネルの **クライアント** メニュー項目と同様の結果をコマンドレットを使用してどのように実現できるのかについて説明します。

この記事では、次のサブメニューについて説明します。

- [クライアント](#client)
  - [クライアント バージョン ポリシー](#client-version-policy)
  - [クライアント バージョンの構成](#client-version-configuration)
  - [デバイス更新](#device-update)
  - [テスト デバイス](#test-device)
  - [デバイス ログの構成](#device-log-configuration)
  - [デバイス構成](#device-configuration)
  - [モビリティ ポリシー](#mobility-policy)
  - [プッシュ通知の構成](#push-notification-configuration)

## <a name="client-version-policy"></a>クライアント バージョン ポリシー

[**クライアント] メニューの [クライアント バージョン ポリシー** ] サブメニュー **項目は、** クライアント環境でサポートされているクライアントSkype for Business Serverします。 クライアント バージョン ポリシーを使用すると、システムにサインインできるクライアントをSkype for Business Serverできます。

クライアント バージョン ポリシーでユーザーが実行できるさまざまなタスクと、それらのタスクがマップSkype for Businessコマンドレットについて検討します。

---
> **シナリオ 1**: すべてのクライアント バージョン ポリシーを一覧表示する

   ![クライアント バージョン ポリシーの一覧表示](./media/clientversionpolicy-1.png)

***コマンドレット***

[Get-CsClientVersionPolicy](/powershell/module/skype/get-csclientversionpolicy)

***例***

```powershell
 Get-CsClientVersionPolicy
```

---

> **シナリオ 2:** 新しいクライアント バージョン ポリシーを作成する

   ![新しいクライアント バージョン ポリシー](./media/clientversionpolicy-2.png)

***コマンドレット***

[New-CsClientVersionPolicy](/powershell/module/skype/new-csclientversionpolicy)  

***例***

```powershell
 New-CsClientVersionPolicy -Identity site:Redmond
```

---

> **シナリオ 3:** 選択したクライアント バージョン ポリシーの詳細を取得する

   ![クライアント バージョン ポリシーの取得](./media/clientversionpolicy-3.png)

***コマンドレット***

[Get-CsClientVersionPolicy](/powershell/module/skype/get-csclientversionpolicy)

***例***

```powershell
 Get-CsClientVersionPolicy -Identity site:Redmond
```

---

> **シナリオ 4:** 選択したクライアント バージョン ポリシーを削除する

   ![クライアント バージョン ポリシーの削除](./media/clientversionpolicy-4.png)

***コマンドレット***

[Remove-CsClientVersionPolicy](/powershell/module/skype/remove-csclientversionpolicy)

***例***

```powershell
 Remove-CsClientVersionPolicy -Identity site:Redmond
```

---

> **シナリオ 5:** クライアント バージョン ポリシーを更新する

   ![クライアント バージョン ポリシーの更新](./media/clientversionpolicy-5.png)

- **注釈 1 - 結果**

    画像上のこの注釈は、結果、つまり取得および表示されるデータを示します。

    ***コマンドレット***

    [Get-CsClientVersionPolicyRule](/powershell/module/skype/get-csclientversionpolicyrule)

    ***例***

    ```powershell
    Get-CsClientVersionPolicyRule -Filter "Global/*"
    ```

- **注釈 2 - オプション (ユーザーの場合)**

    イメージ上のこの注釈は、ユーザーがクライアント バージョン ポリシー ルールの詳細を取得するために実装するオプションを示します。

    ***コマンドレット***

    [Get-CsClientVersionPolicyRule](/powershell/module/skype/get-csclientversionpolicyrule)

    ***例***

    ```powershell
    Get-CsClientVersionPolicyRule -Identity "Global/2336c611-a243-4c5d-994b-eea8a524d0e4"
    ```

- **注釈 3 - オプション (ユーザーの場合)**

    イメージ上のこの注釈は、ユーザーが新しいクライアント バージョン ポリシー ルールを作成するために実装するオプションを示します。

    ***コマンドレット***

    [New-CsClientVersionPolicyRule](/powershell/module/skype/new-csclientversionpolicyrule)

    ***例***

    ```powershell
    $x = \[guid\]::NewGuid()

    New-CsClientVersionPolicyRule -Parent "site:Redmond" -RuleId $x -MajorVersion 4 -UserAgent InHouse
    ```

- **注釈 4 - オプション (ユーザーの場合)**

    イメージ上のこの注釈は、ユーザーが新しく作成したクライアント バージョン ポリシー ルールをコミット/保存するためのオプションを示します。

    ***コマンドレット***

    [Set-CsClientVersionPolicy](/powershell/module/skype/set-csclientversionpolicy)

    ***例***

    ```powershell
    Set-CsClientVersionPolicy -Identity site:Redmond -Rules $Null

    $x = Get-CsClientVersionPolicy -Identity site:Dublin | Select-Object -ExpandProperty Rules

    Set-CsClientVersionPolicy -Identity site:Redmond -Rules $x
    ```

---

## <a name="client-version-configuration"></a>クライアント バージョンの構成

 [**クライアントバージョン構成]** サブメニュー項目は、環境でサポートされているクライアントに関するSkype for Business Serverします。

クライアントバージョン構成でユーザーが実行できるさまざまなタスクと、それらのタスクがマップSkype for Businessコマンドレットについて検討します。

---
> **シナリオ 1**: すべてのクライアント バージョン構成を一覧表示する

   ![クライアント バージョンの構成の一覧表示](./media/ClientVersionConfiguration-1.png)

***コマンドレット***

[Get-CsClientVersionConfiguration](/powershell/module/skype/get-csclientversionconfiguration)

***例***

```powershell
 Get-CsClientVersionConfiguration
```

---

> **シナリオ 2:** 新しいクライアント バージョン構成を作成する

   ![クライアント バージョン構成の作成](./media/ClientVersionConfiguration-2.png)

***コマンドレット***

[New-CsClientVersionConfiguration](/powershell/module/skype/new-csclientversionconfiguration)  

***例***

```powershell
 New-CsClientVersionConfiguration -Identity site:Redmond -Enabled $False
```

---

> **シナリオ 3:** 選択したクライアント バージョン構成の詳細を取得する

   ![クライアント バージョン構成の取得](./media/ClientVersionConfiguration-3.png)

***コマンドレット***

[Get-CsClientVersionConfiguration](/powershell/module/skype/get-csclientversionconfiguration)

***例***

```powershell
 Get-CsClientVersionConfiguration -Identity site:Redmond
```

---

> **シナリオ 4:** 選択したクライアント バージョン構成を削除する

   ![クライアント バージョン構成の削除](./media/ClientVersionConfiguration-4.png)

***コマンドレット***

[Remove-CsClientVersionConfiguration](/powershell/module/skype/remove-csclientversionconfiguration)

***例***

```powershell
 Remove-CsClientVersionConfiguration -Identity site:Redmond
```

---

> **シナリオ 5**: クライアント バージョンの構成を更新する

   ![クライアント バージョン構成の更新](./media/ClientVersionConfiguration-5.png)

***コマンドレット***

[Set-CsClientVersionConfiguration](/powershell/module/skype/set-csclientversionconfiguration)

***例***

```powershell
Get-CsClientVersionConfiguration | Set-CsClientVersionConfiguration -DefaultURL "https://litwareinc.com/csclients"
```

---

> **シナリオ 6:** クライアント バージョンの構成を有効または無効にする

![クライアント バージョンの構成を有効にする](./media/ClientVersionConfiguration-6.png)

***コマンドレット***

[Set-CsClientVersionConfiguration](/powershell/module/skype/set-csclientversionconfiguration)

***例***

```powershell
Set-CsClientVersionConfiguration -Identity site:Redmond -Enabled $False
```

---

## <a name="device-update"></a>デバイス更新

**DEVICE UPDATE ルール** は、ファームウェア更新プログラムをエディションで実行するデバイスに関連付Skype for Business 電話されます。

DEVICE **UPDATE** でユーザーが実行できるさまざまなタスクと、それらのタスクがマップSkype for Businessするコマンドレットについて説明します。

---
> **シナリオ 1**: すべてのデバイス更新プログラムを一覧表示する

   ![デバイスの更新の一覧](./media/device-update-1.png)

***コマンドレット***

[Get-CsDeviceUpdateRule](/powershell/module/skype/get-csdeviceupdaterule)

***例***

```powershell
 Get-CsDeviceUpdateRule
```

---

> **シナリオ 2:** デバイス更新プログラムの削除

   ![デバイス更新プログラムの削除](./media/device-update-2.png)

***コマンドレット***

[Remove-CsDeviceUpdateRule](/powershell/module/skype/remove-csdeviceupdaterule)  

***例***

```powershell
 Remove-CsDeviceUpdateRule -Identity service:WebServer:atl-cs-001.litwareinc.com/d5ce3c10-2588-420a-82ac-dc2d9b1222ff9
```

---

> **シナリオ 3:** デバイスの更新をキャンセルする

   ![デバイス更新の取り消し](./media/device-update-3.png)

***コマンドレット***

[Clear-CsDeviceUpdateFile](/powershell/module/skype/clear-csdeviceupdatefile)

***例***

```powershell
 Clear-CsDeviceUpdateFile -Identity "service:WebServer:atl-cs-001.litwareinc.com"
```

---

> **シナリオ 4:** デバイスの更新を承認する

   ![デバイスの更新を承認する](./media/device-update-4.png)

***コマンドレット***

[Approve-CsDeviceUpdateRule](/powershell/module/skype/approve-csdeviceupdaterule)

***例***

```powershell
 Approve-CsDeviceUpdateRule -Identity service:WebServer:atl-cs-001.litwareinc.com/d5ce3c10-2588-420a-82ac-dc2d9b1222ff9
```

---

> **シナリオ 5:** デバイスの更新プログラムを復元する

   ![デバイス更新プログラムの復元](./media/device-update-5.png)

***コマンドレット***

[Restore-CsDeviceUpdateRule](/powershell/module/skype/restore-csdeviceupdaterule)

***例***

```powershell
 Restore-CsDeviceUpdateRule -Identity service:WebServer:atl-cs-001.litwareinc.com/d5ce3c10-2588-420a-82ac-dc2d9b1222ff9
```

---

## <a name="test-device"></a>テスト デバイス

**TEST DEVICE サブ** メニュー項目は、管理者がファームウェア更新プログラムをテストしてから、それらの更新プログラムを組織内のすべてのデバイスに配布する方法を提供します。

TEST **DEVICE** でユーザーが実行できるさまざまなタスクと、それらのタスクがマップSkype for Businessコマンドレットについて検討します。

---
> **シナリオ 1**: すべてのテスト デバイスを一覧表示する

   ![テスト デバイスの一覧](./media/testdevice-1.png)

***コマンドレット***

[Get-CsTestDevice](/powershell/module/skype/get-cstestdevice)

***例***

```powershell
 Get-CsTestDevice
```

---

> **シナリオ 2:** 新しいテスト デバイスを作成する

   ![テスト デバイスの作成](./media/testdevice-2.png)

***コマンドレット***

[New-CsTestDevice](/powershell/module/skype/new-cstestdevice)  

***例***

```powershell
 New-CsTestDevice -Identity site:Redmond/UCPhone -IdentifierType SerialNumber -Identifier "07823-A345"
```

---

> **シナリオ 3:** 選択したテスト デバイスの詳細を取得する

   ![テスト デバイスの取得](./media/testdevice-3.png)

***コマンドレット***

[Get-CsTestDevice](/powershell/module/skype/get-cstestdevice)

***例***

```powershell
 Get-CsTestDevice -Identity site:Redmond/UCPhone
```

---

> **シナリオ 4:** 選択したテスト デバイスを削除する

   ![テスト デバイスの削除](./media/testdevice-4.png)

***コマンドレット***

[Remove-CsTestDevice](/powershell/module/skype/remove-cstestdevice)

***例***

```powershell
 Remove-CsTestDevice -Identity site:Redmond
```

---

> **シナリオ 5:** テスト デバイスを更新する

   ![テスト デバイスの更新](./media/testdevice-5.png)

***コマンドレット***

[Set-CsTestDevice](/powershell/module/skype/set-cstestdevice)

***例***

```powershell
Set-CsTestDevice -Identity site:Redmond/UCPhone -IdentifierType SerialNumber -Identifier "09768-ABDR-83295"
```

---

## <a name="device-log-configuration"></a>デバイス ログの構成

**DEVICE LOG CONFIGURATION** サブメニュー項目は、管理者がファームウェア更新プログラムを電話や Skype for Business を実行する他のデバイスにファームウェア更新プログラムを配布できる Skype for Business Server コンポーネントである Device Update Web サービスを管理するのに役立ちます。

DEVICE **LOG** 構成でユーザーが実行できるさまざまなタスクと、それらのタスクがマップSkype for Businessコマンドレットについて検討します。

---
> **シナリオ 1**: すべてのデバイス ログ構成を一覧表示する

   ![デバイス ログの構成を一覧表示する](./media/device-log-configuration-1.png)

***コマンドレット***

[Get-CsDeviceUpdateConfiguration](/powershell/module/skype/get-csdeviceupdateconfiguration)

***例***

```powershell
 Get-CsDeviceUpdateConfiguration
```

---

> **シナリオ 2:** 新しいデバイス ログ構成を作成する

   ![デバイス ログの構成を作成する](./media/device-log-configuration-2.png)

***コマンドレット***

[New-CsDeviceUpdateConfiguration](/powershell/module/skype/new-csdeviceupdateconfiguration)  

***例***

```powershell
 New-CsDeviceUpdateConfiguration -Identity site:Redmond "07823-A345"
```

---

> **シナリオ 3:** 選択したデバイス ログ構成の詳細を取得する

   ![デバイス ログの構成を取得する](./media/device-log-configuration-3.png)

***コマンドレット***

[Get-CsDeviceUpdateConfiguration](/powershell/module/skype/get-csdeviceupdateconfiguration)

***例***

```powershell
 Get-CsDeviceUpdateConfiguration -Identity Global
```

---

> **シナリオ 4:** 選択したデバイス ログ構成を削除する

   ![デバイス ログの構成の削除](./media/device-log-configuration-4.png)

***コマンドレット***

[Remove-CsDeviceUpdateConfiguration](/powershell/module/skype/remove-csdeviceupdateconfiguration)

***例***

```powershell
 Remove-CsDeviceUpdateConfiguration -Identity site:Redmond
```

---

> **シナリオ 5:** デバイス ログの構成を更新する

   ![デバイス ログの構成の更新](./media/device-log-configuration-5.png)

***コマンドレット***

[Set-CsDeviceUpdateConfiguration](/powershell/module/skype/set-csdeviceupdateconfiguration)

***例***

```powershell
Set-CsDeviceUpdateConfiguration -Identity global -MaxLogFileSize 2048000 -MaxLogCacheLimit 1024000
```

---

## <a name="device-configuration"></a>デバイス構成

**DEVICE CONFIGURATION** サブメニュー項目は、UC 電話の管理オプションに関する情報を管理するのに役立ちます。 これらのオプションには、必要なセキュリティ モードと、指定された非アクティブ期間が終了した後に電話を自動的にロックするかどうかを指定します。

DEVICE **CONFIGURATION** でユーザーが実行できるさまざまなタスクと、それらのタスクがマップSkype for Businessするコマンドレットについて説明します。

---

> **シナリオ 1**: すべてのモビリティ ポリシーを一覧表示する

   ![デバイスの構成の一覧](./media/device-configuration-1.png)

***コマンドレット***

[Get-CsUCPhoneConfiguration](/powershell/module/skype/get-csucphoneconfiguration)

***例***

```powershell
 Get-CsUCPhoneConfiguration
```

---

> **シナリオ 2:** 新しいデバイス構成を作成する

   ![デバイス構成の作成](./media/device-configuration-2.png)

***コマンドレット***

[New-CsUCPhoneConfiguration](/powershell/module/skype/new-csucphoneconfiguration)  

***例***

```powershell
 New-CsUCPhoneConfiguration -Identity site:Redmond -CalendarPollInterval "00:10:00" -LoggingLevel "Medium"
```

---

> **シナリオ 3:** 選択したデバイス構成の詳細を取得する

   ![デバイス構成の取得](./media/device-configuration-3.png)

***コマンドレット***

[Get-CsUCPhoneConfiguration](/powershell/module/skype/get-csucphoneconfiguration)

***例***

```powershell
 Get-CsUCPhoneConfiguration -Identity site:Redmond
```

---

> **シナリオ 4:** 選択したデバイス構成を削除する

   ![デバイス構成の削除](./media/device-configuration-4.png)

***コマンドレット***

[Remove-CsUCPhoneConfiguration](/powershell/module/skype/remove-csucphoneconfiguration)

***例***

```powershell
 Remove-CsUCPhoneConfiguration -Identity site:Redmond
```

---

> **シナリオ 5:** デバイス構成を更新する

   ![デバイス構成の更新](./media/device-configuration-5.png)

***コマンドレット***

[Set-CsUCPhoneConfiguration](/powershell/module/skype/set-csucphoneconfiguration)

***例***

```powershell
 Set-CsUCPhoneConfiguration -Identity site:Redmond -PhoneLockTimeout "00:30:00"
```

---

## <a name="mobility-policy"></a>モビリティ ポリシー

**MOBILITY POLICY は**、ユーザーがモバイルデバイスを使用できるかどうかをSkype for Businessします。 また、ユーザーが [勤務先から通話] を使用する機能、つまり、ユーザーが携帯電話で、携帯電話の番号ではなく勤務先の電話番号を使用して通話を発信および受信できるようにする機能も管理します。 モビリティ ポリシーを使用して、通話のWi-Fi受信時に接続を要件とすることができます。

MOBILITY **POLICY** でユーザーが実行できるさまざまなタスクと、それらのタスクがマップSkype for Businessするコマンドレットについて説明します。

---

> **シナリオ 1**: すべてのモビリティ ポリシーを一覧表示する

   ![リスト モビリティ ポリシー](media/mobility-policy-1.png)

***コマンドレット***

[Get-CsMobilityPolicy](/powershell/module/skype/get-csmobilitypolicy)

***例***

```powershell
 Get-CsMobilityPolicy
```

---

> **シナリオ 2:** 新しいモビリティ ポリシーを作成する

   ![モビリティ ポリシーの作成](./media/mobility-policy-2.png)

***コマンドレット***

[New-CsMobilityPolicy](/powershell/module/skype/new-csmobilitypolicy)  

***例***

```powershell
 New-CsMobilityPolicy -Identity site:Redmond -EnableOutsideVoice $False
```

---

> **シナリオ 3:** 選択したモビリティ ポリシーの詳細を取得する

   ![モビリティ ポリシーの取得](./media/mobility-policy-3.png)

***コマンドレット***

[Get-CsMobilityPolicy](/powershell/module/skype/get-csmobilitypolicy)

***例***

```powershell
 Get-CsMobilityPolicy -Identity "site:Redmond"
```

---

> **シナリオ 4**: 選択したモビリティ ポリシーを削除する

   ![モビリティ ポリシーの削除](./media/mobility-policy-4.png)

***コマンドレット***

[Remove-CsMobilityPolicy](/powershell/module/skype/remove-csmobilitypolicy)

***例***

```powershell
 Remove-CsMobilityPolicy -Identity "site:Redmond"
```

---

> **シナリオ 5:** モビリティ ポリシーを更新する

   ![モビリティ ポリシーの更新](./media/mobility-policy-5.png)

***コマンドレット***

[Set-CsMobilityPolicy](/powershell/module/skype/set-csmobilitypolicy)

***例***

```powershell
Set-CsMobilityPolicy -Identity "site:Redmond" -EnableOutsideVoice $False
```

---

## <a name="push-notification-configuration"></a>プッシュ通知の構成

プッシュ通知サービス (Apple プッシュ通知サービスおよび Microsoft プッシュ通知サービス) は、新しいインスタント メッセージや新しいボイス メールなどのイベントに関する通知を、iPhone や Windows Phone などのモバイル デバイスに送信する方法を提供します。 これらの通知は、それらのデバイス上の Skype for Businessアプリケーションが現在中断またはバックグラウンドで実行されている場合でも送信するように構成されます。

プッシュ通知構成でユーザーが実行できるさまざまなタスクと、それらのタスクがマップSkype for Businessコマンドレットについて説明します。

---

> **シナリオ 1**: すべてのモビリティ ポリシーを一覧表示する

   ![プッシュ通知の構成の一覧](./media/push-notification-config-1.png)

***コマンドレット***

[Get-CsPushNotificationConfiguration](/powershell/module/skype/get-cspushnotificationconfiguration)

***例***

```powershell
 Get-CsPushNotificationConfiguration
```

---

> **シナリオ 2:** 新しいプッシュ通知構成を作成する

   ![プッシュ通知構成の作成](./media/push-notification-config-2.png)

***コマンドレット***

[New-CsPushNotificationConfiguration](/powershell/module/skype/new-cspushnotificationconfiguration)  

***例***

```powershell
 New-CsPushNotificationConfiguration -Identity "site:Redmond" -EnableApplePushNotificationService $True -EnableMicrosoftPushNotificationService -$True
```

---

> **シナリオ 3:** 選択したプッシュ通知構成の詳細を取得する

   ![プッシュ通知の構成を取得する](./media/push-notification-config-3.png)

***コマンドレット***

[Get-CsPushNotificationConfiguration](/powershell/module/skype/get-cspushnotificationconfiguration)

***例***

```powershell
 Get-CsPushNotificationConfiguration -Identity "site:Redmond"
```

---

> **シナリオ 4**: 選択したプッシュ通知構成を削除する

   ![プッシュ通知の構成の削除](./media/push-notification-config-4.png)

***コマンドレット***

[Remove-CsPushNotificationConfiguration](/powershell/module/skype/remove-cspushnotificationconfiguration)

***例***

```powershell
 Remove-CsPushNotificationConfiguration -Identity "site:Redmond"
```

---

> **シナリオ 5:** プッシュ通知の構成を更新する

   ![プッシュ通知の構成の更新](./media/push-notification-config-5.png)

***コマンドレット***

[Set-CsPushNotificationConfiguration](/powershell/module/skype/set-cspushnotificationconfiguration)

***例***

```powershell
 Set-CsPushNotificationConfiguration -Identity "site:Redmond" -EnableApplePushNotificationService $False
```

---
