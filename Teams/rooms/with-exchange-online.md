---
title: Exchange Online を使用して Microsoft Teams Rooms を展開
ms.author: czawideh
author: cazawideh
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
ms.custom: ''
ms.assetid: f3ba85b8-442c-4133-963f-76f1c8a1fff9
description: このトピックでは、会議室と会議室をデプロイするMicrosoft TeamsをExchange Online。
ms.openlocfilehash: ad3b621ef541fcec471e329d1696e4f7000f4cb5
ms.sourcegitcommit: a894e9397050e09bfaab02e700e943a3bbeb1302
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/15/2022
ms.locfileid: "63503744"
---
# <a name="deploy-microsoft-teams-rooms-with-exchange-online"></a>Exchange Online を使用して Microsoft Teams Rooms を展開

このトピックでは、会議室と会議室をデプロイするMicrosoft TeamsをExchange Online。
  
組織にサービスが混在していて、オンプレミスとオンラインでホストされているものがある場合、構成は各サービスのホスト場所によって異なります。 このトピックでは Exchangeがオンラインでホストする、Microsoft Teams Rooms のハイブリッドな展開について説明します。 この種類の展開には、さまざまな違いがあるため、すべての手順を詳細に説明することはできません。 次のプロセスは、多くの構成で機能します。 このプロセスがユーザーのセットアップに適していない場合は、Windows PowerShell を使用して、ここに記載されているのと同じ結果を達成するか、または他の展開オプションをお勧めします。

## <a name="requirements"></a>要件

Microsoft Teams Rooms を Exchange Onlineで展開する前に、要件を満たしていることをご確認ください。 詳細については、「[Microsoft Teams Rooms の要件](requirements.md)」をご覧ください。
  
Exchange Online を使用して Microsoft Teams Rooms を展開するには、次の手順に従います。 コマンドレットを実行するための適切なアクセス許可を持っている必要があります。 

   > [!NOTE]
   >  この[Azure Active Directoryの](/powershell/azure/active-directory/overview?view=azureadps-1.0) Windows PowerShell 用モジュール (Set-MsolUser など) は、Microsoft Teams Rooms のアカウントの設定でテストされています。 他のコマンドレットでも機能することがありますが、この特定のシナリオではテストされていません。

Active Directory フェデレーションサービス (AD FS) を展開した場合は、次の手順を実行する前に、ユーザーアカウントを管理されているユーザーに変換し、この手順を実行した後にユーザーをフェデレーションユーザーに戻す必要があります。
  
### <a name="create-an-account-and-set-exchange-properties"></a>アカウントを作成して、Exchange のプロパティを設定する

1. PC でリモートの Windows PowerShell セッションを開始し、次のように Exchange Online に接続します。

    ``` Powershell
   Connect-ExchangeOnline
    ```

2. セッションを確立したら、新しいメールボックスを作成して、それを RoomMailboxAccount として有効にするか、既存の会議室メールボックスの設定を変更します。 これにより、アカウントは、Microsoft Teams Roomsに認証されます。

   既存のリソースメールボックスを変更する場合：

   ``` Powershell
   Set-Mailbox -Identity 'ConferenceRoom01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

    新しいリソース メールボックスを作成している場合:

   ``` Powershell
   New-Mailbox -MicrosoftOnlineServicesID 'ConferenceRoom01@contoso.com' -Alias ConferenceRoom01 -Name 'ConferenceRoom01' -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

3. 会議のエクスペリエンスを改善するには、ユーザー アカウントで、次のように Exchangeプロパティを設定する必要があります。

   ``` Powershell
   Set-CalendarProcessing -Identity 'ConferenceRoom01@contoso.com' -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity 'ConferenceRoom01@contoso.com' -AddAdditionalResponse $true -AdditionalResponse "This is a Microsoft Teams Rooms enabled  room!"
   ```

### <a name="add-an-email-address-for-your-on-premises-domain-account"></a>オンプレミスのドメインアカウントのメールアドレスを追加する

1. **Active Directory UsersおよびComputers AD** ツールで、コンテナーまたMicrosoft Teams Rooms のアカウントの作成先となる組織単位を右クリックし、**新規** そして **ユーザー** の順にクリックします。
2. 前のコマンドレット(Set-MailboxまたはNew-Mailbox)の表示名 (- Identity )を **フルネーム** ボックスに入力し、次にアリアスを **ユーザーログイン名** ボックスに入力します。 **[次へ]** をクリックします。
3. このアカウントのパスワードを入力します。確認のためにもう一度入力する必要があります。[**パスワードを無期限にする**] チェック ボックスだけがオンになっていることを確認します。

    > [!NOTE]
    > [パスワードの **有効期限が切れることはありません**] を選択すると、Microsoft Teamsされます。 有効期限が切れないパスワードは、ドメインのルールで禁止されるかもしれません。 その場合は、Microsoft Teams Rooms のユーザーアカウントごとに例外を作成する必要があります。
  
4. [ **完了**] をクリックしてアカウントを作成します。
5. アカウントを作成したら、ディレクトリの同期を実行します。 これを行うには、PowerShell で[Set-MsolDirSyncConfiguration](/powershell/module/msonline/set-msoldirsyncconfiguration?view=azureadps-1.0)を使用します。 完了したら、ユーザーのページに移動し、前の手順で作成した 2 つのアカウントがマージされたと確認します。

### <a name="assign-an-office-365-license"></a>Office 365 ライセンスを割り当てる

1. 最初にAzure AD に接続して、アカウント設定をいくつか適用する必要があります。 このコマンドレットを実行して接続できます。 Active Directory の詳細については、[Azure ActiveDirectory (MSOnline) 1.0](/powershell/azure/active-directory/overview?view=azureadps-1.0)を参照してください。

   > [!NOTE]
   > [Azure Active Directory PowerShell 2.0](/powershell/azure/active-directory/overview?view=azureadps-2.0) はサポートされていません。

    ``` PowerShell
   Connect-MsolService
    ```

2. ユーザー アカウントに接続するには、ユーザー アカウントに有効Office 365ライセンスが必要Microsoft Teams。 ライセンスを所有している場合は、使用場所をユーザーアカウントに割り当てる必要があります。これにより、アカウントに使用できるライセンス SKU が決まります。
3. "Get-MsolAccountSku" を使用して、テナントで使用可能な SKU の一覧Office 365します。
4. SKU を一覧表示したら、'Set-MsolUserLicense' を使用してライセンスを追加できます。 <!-- Set-AzureADUserLicense--> することができます。 

    ```PowerShell
     Set-MsolUser -UserPrincipalName 'ConferenceRoom01@contoso.com' -UsageLocation 'US'
     Get-MsolAccountSku
     Set-MsolUserLicense -UserPrincipalName 'ConferenceRoom01@contoso.com' -AddLicenses 'contoso:MEETING_ROOM
    ```

## <a name="validate"></a>検証

検証の場合は、任意のクライアント クライアントMicrosoft Teamsして、作成したアカウントにサインインできます。
  
## <a name="see-also"></a>関連項目

[検索とルームの候補エクスペリエンスを向上するために、追加のメタデータでルーム メールボックスを更新する](/powershell/module/exchange/set-place)

[Microsoft Teams Rooms のアカウントを構成する](rooms-configure-accounts.md)

[Microsoft Teams Rooms を計画する](rooms-plan.md)
  
[Microsoft Teams Rooms をデプロイする](rooms-deploy.md)
  
[Microsoft Teams Rooms コンソールを構成する](console.md)
  
[Microsoft Teams Rooms を管理する](rooms-manage.md)
