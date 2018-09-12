---
title: サーフェスのハブのマイクロソフトのチームを配置します。
author: ChuckEdmonson
ms.author: chucked
manager: serdars
ms.date: 08/29/2018
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: jatpatel
description: サーフェスのハブのマイクロソフトのチームの管理の設定を構成します。
localization_priority: Normal
search.appverid: MET150
ms.custom:
- Devices
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 251cc2d12dfdab2e9bc4c9bcc928e80a9c43e2c2
ms.sourcegitcommit: 6732f56535d60a46e6998cde64103e8530dd6452
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/11/2018
ms.locfileid: "23938001"
---
<a name="deploy-microsoft-teams-for-surface-hub"></a>サーフェスのハブのマイクロソフトのチームを配置します。
======================================

Microsoft Surface のハブのマイクロソフトのチームを配置する前に、ハードウェア、オペレーティング システム、およびその他の要件を満たしていることを確認してください。 詳細については、 [Microsoft Surface ハブ管理者ガイド](https://docs.microsoft.com/surface-hub/)を参照してください。

## <a name="set-up-user-accounts"></a>ユーザー アカウントを設定します
 
サーフェスのハブのチームと共同で使用できるユーザー アカウントを設定するには、ビジネスの Skype でのサポートと同様、デバイスのアカウントを作成します。 デバイスのアカウントが必要複数要素の認証が無効になります (自動ログオンを許可する) Office 365 でのチームの次の依存するサービスです。  
- Exchange 
- SharePoint 
- Office アプリケーション 

## <a name="add-a-device-account"></a>デバイス アカウントを追加する 

1\。 PC 上でリモートの Windows PowerShell セッションを開始し、Exchange に接続します。 関連付けられているコマンドレットを実行する適切なアクセス許可があることを確認します。 環境で使用し、変更できるコマンドレットの例を次に示します。

```
Set-ExecutionPolicy Unrestricted
$org='contoso.com'
$cred=Get-Credential $admin@$org
$sess= New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ 
-Credential $cred -Authentication Basic -AllowRedirection
Import-PSSession $sess
```

2\。 セッションを確立したら、新しいメールボックスを作成して RoomMailboxAccount として有効にするか、既存の会議室メールボックスの設定を変更します。 これにより、チームへの認証にアカウントが許可されます。

既存のリソース メールボックスを変更している場合:

```
Set-Mailbox -Identity 'TEAMS01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
```

新しいリソース メールボックスを作成している場合:

```
New-Mailbox -MicrosoftOnlineServicesID TEAMS01@contoso.com -Alias TEAMS01 
-Name "Teams-01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword
 (ConvertTo-SecureString -String <password> -AsPlainText -Force)
```

3\。 会議エクスペリエンスを改善するために、さまざまな Exchange プロパティをデバイス アカウントに設定する必要があります。 設定する必要のあるプロパティは、「Exchange のプロパティ」セクションで確認できます。

```
Set-CalendarProcessing -Identity $acctUpn -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments $false
 -DeleteSubject $false -RemovePrivateProperty $false
Set-CalendarProcessing -Identity $acctUpn -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
```

4\。 Azure Active Directory に接続して、アカウント設定をいくつか適用する必要があります。 Azure AD に接続するには、次のコマンドレットを実行します。

```
Connect-MsolService -Credential $cred
```

5\。 	パスワードを無期限にする場合は、次のように Set-MsolUser コマンドレットに PasswordNeverExpires オプションを付けて実行します。 

```
Set-MsolUser -UserPrincipalName $acctUpn -PasswordNeverExpires $true
```

次のように、会議室の電話番号を設定することもできます。

```
Set-MsolUser -UniversalPrincipalName <upn> -PhoneNumber <phone number>
```

6\。 デバイスのアカウントは、有効な Office 365 のライセンスでは、する必要があるか、Exchange およびビジネス用の Skype は機能しません。 ライセンスがあれば、利用場所を割り当てる、デバイスのアカウントにする必要があります-どのようなライセンスは、アカウントの利用可能な決定します。 Get MsolAccountSku を使用して、次のように、Office 365 テナントの使用可能な Sku の一覧を取得できます。
 
```
Get-MsolAccountSku
```

次に、Set-MsolUserLicense コマンドレットを使用して、ライセンスを追加することができます。この場合、表示される SKU コードは $strLicense です (たとえば、contoso:STANDARDPACK)。

```
Set-MsolUser -UserPrincipalName $acctUpn -UsageLocation "US"
Get-MsolAccountSku
Set-MsolUserLicense -UserPrincipalName $acctUpn -AddLicenses $strLicense
```

7\。 次に、サーフェスのハブのチームを持つデバイスのアカウントを有効にする必要があります。 お客様の環境は、 [Microsoft Surface ハブ管理者ガイド 』](https://docs.microsoft.com/surface-hub/)で定義されている要件を満たしていることを確認します。

次のように、リモートの Windows PowerShell セッションを開始 (オンライン PowerShell のビジネス コンポーネントの Skype をインストールすることを確認する)。

```
Import-Module LyncOnlineConnector
$cssess=New-CsOnlineSession -Credential $cred  
Import-PSSession $cssess -AllowClobber
```

次に、次のコマンドレットを実行して、サーフェスのハブのアカウントに、チームを有効にします。

```
Enable-CsMeetingRoom -Identity $rm -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
```

次の使用例に示すように、新しいユーザー アカウントのセットアップの中から RegistrarPool 情報を取得します。

```
Get-CsOnlineUser -Identity $rm | Select -Expand RegistrarPool
```

> [!NOTE]
> テナント内の既存のユーザー アカウントとして同じレジストラー プールに新しいユーザー アカウントを作成できません可能性があります。 上記のコマンドは、このような状況が発生したため、アカウントのセットアップでエラーをできなくなります。 

サーフェスのハブのアカウントに、チームを有効にするのには、上記の手順を完了した後は、サーフェスのハブ v2 デバイスにライセンスを割り当てる必要があります。 Office 365 管理ポータルを使用して、デバイスに、チームでのサーフェスのハブのライセンスを割り当てます。

### <a name="assign-a-license-to-the-account"></a>アカウントにライセンスを割り当てます。

1. テナント管理者としてログオンし、Office 365 管理センターで、開き [管理アプリケーション] をクリックします。
2. **ユーザーとグループ**をクリックし、**ユーザーの追加、パスワードのリセット**] をクリックします。
3. サーフェスのハブのアカウント チームを選択しを手段の編集 [ペン] アイコンをタップします。
4. **ライセンス**オプションをクリックします。
5. [**ライセンスの割り当て**] セクションで、ライセンスによって、プランを選択する必要があります。
6. タスクを完了するには、**[保存]** をクリックします。

## <a name="install-teams-for-surface-hub-from-the-microsoft-store"></a>Microsoft ストアからのサーフェスのハブのチームをインストールします。 

これらは、Microsoft ストアからのサーフェスのハブのチームをインストールします。 
 
1. マイクロソフトのストアを開始します。<br>
   a. **スタート**をタップして > **すべてのアプリケーション** > **の設定**です。<br> b. **サーフェス ハブ デバイスのアカウント、管理**をタップします。<br>
   c. 左側の [**アプリケーションと機能**] タブをタップします。<br> d. 、右側には、**ストアを開く**] ボタンをタップします。 
2. マイクロソフト ストアからには、*マイクロソフトのチーム*を検索します。 **サーフェスのハブのマイクロソフトのチーム**が表示されます。 インストールする**アプリケーションを取得する**ボタンをタップします。  
3. インストールが完了すると、サーフェスのハブを再起動します。 

> [!NOTE]
> ページを一覧表示するストアからの**起動**をタップしないようにします。

## <a name="make-teams-the-default-calling-and-meetings-application"></a>デフォルトの通話や会議アプリケーションは、チームを作成します。
 
通話や会議アプリケーションの既定ポリシーを構成するための 2 つのオプションがあります。 

- **オプション 1**: USB キーを使用して構成します。 
- **オプション 2**: Intune などの MDM を使用して構成します。
 
### <a name="option-1-configure-via-usb-key"></a>オプション 1: は、USB キーを使用して構成します。 
 
この[ダウンロード ページ](https://1drv.ms/f/s!ArcnbnREun0Vnp9Wps9MlWB-UJZw3g)で、パッケージをご覧ください。 適切なパッケージをインストールし、USB キーにコピーする予定しているを選択します。 正しい .ppkg ファイルを使用するのには、次のように適用するにはアプリケーションの既定のポリシーによって異なります。 

|数値  |説明  |
|---------|---------|
|0     | [開始] 画面で [チームの会議が利用可能な Skype 優先のアプリケーション        |
|1     | チーム優先のアプリケーション起動画面で、利用可能な Skype の会議        |
|2     | チームの排他的なアプリケーション (Skype アプリが利用できない) の開始画面        |
 
1. サーフェス ハブ デバイスに USB キーを接続します。 
2. サーフェス ハブ デバイスの**設定**アプリを開きます。 
3. **表面ハブ デバイスのアカウントの管理**を開きます。
4. **デバイスの管理**を開きます。 
5. **追加またはプロビジョニング ・ パッケージを削除する**] をクリックします。 
6. **パッケージの追加**] をクリックします。
7. ドロップ ダウン メニューから、[**リムーバブル メディア**] オプションを選択します。 
8. 以前、USB キーにコピーされた適切な**TeamsRTMMode*.ppkg**パッケージを追加します。 
9. サーフェス ハブ デバイスを再起動します。 
10. デバイスを再起動した後は、開始画面から、チームのアプリケーションを起動し、カレンダーから会議に参加することができます。 

### <a name="option-2-configure-via-mdm-such-as-intune"></a>Intune などの MDM を使用してオプション 2: を構成します。 

Intune を使用して既定の通話や会議のアプリケーション ポリシーを構成するのにには、次を使用します。

|設定   |値    |説明    |
|----------|---------|---------|
| Path      | ./Vendor/MSFT/SurfaceHub/Properties/SurfaceHubMeetingMode        |
|データ型 | 整数 (0-2)   |0 - [開始] 画面で [チームの会議が利用可能な Skype 優先のアプリケーション<br>1 のチーム開始画面で、Skype の会議が利用可能なアプリケーションを優先します。<br>2-チームは、開始画面 (Skype アプリケーションではありません排他的なアプリケーション |
|運用| 取得、設定        |

|設定   |値    |
|----------|---------|
| Path      | ./Vendor/MSFT/SurfaceHub/Properties/VtcAppPackageId        |
|データ型 | 文字列 - **Microsoft.MicrosoftTeamsforSurfaceHub_8wekyb3d8bbwe としてチームのアプリケーション パッケージ ID に文字列を設定します。チーム** |
|運用| 取得、設定        |

サーフェス ハブ デバイスを再起動します。 デバイスを再起動した後は、開始画面から、チームのアプリケーションを起動し、カレンダーから会議に参加することができます。

> [!NOTE]
> デバイスや、組織のデバイスは、現在 Windows 内部からのプログラムの一部と全般的なデータ保護規制 (GDPR) で対象となる国では (または基本の遠隔測定の設定を手動で変更がある) 場合は、チェックする必要があります再します。有効に完全な遠隔測定を内部からプログラムに参加する前にします。 GDPR は、基本的な遠隔測定を設定するのには、EU 内のサーフェスのハブ デバイスの既定の動作を変更します。
