---
title: Exchange Online を使用して Microsoft Teams Rooms を展開
ms.author: dstrome
author: dstrome
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
ms.custom: seo-marvel-apr2020
ms.assetid: f3ba85b8-442c-4133-963f-76f1c8a1fff9
description: このトピックでは、Exchange OnlineとSkype for Business Serverオンプレミス を使用して Microsoft Teams Rooms を展開する方法について説明します。
ms.openlocfilehash: 8f8511f4dd05b6d2eb073aaab0a14305c9d67831
ms.sourcegitcommit: 1165a74b1d2e79e1a085b01e0e00f7c65483d729
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/08/2021
ms.locfileid: "61355636"
---
# <a name="deploy-microsoft-teams-rooms-with-exchange-online"></a>Exchange Online を使用して Microsoft Teams Rooms を展開

このトピックでは、会議室と会議室をデプロイするMicrosoft Teams方法について説明Exchange Online。
  
組織にサービスが混在していて、オンプレミスとオンラインでホストされているものがある場合、構成は各サービスのホスト場所によって異なります。 このトピックでは Exchangeがオンラインでホストする、Microsoft Teams Rooms のハイブリッドな展開について説明します。 この種類の展開には、さまざまな違いがあるため、すべての手順を詳細に説明することはできません。 次のプロセスは、多くの構成で機能します。 このプロセスがユーザーのセットアップに適していない場合は、Windows PowerShell を使用して、ここに記載されているのと同じ結果を達成するか、または他の展開オプションをお勧めします。

## <a name="requirements"></a>要件

Microsoft Teams Rooms を Exchange Onlineで展開する前に、要件を満たしていることをご確認ください。 詳細については、「[Microsoft Teams Rooms の要件](requirements.md)」をご覧ください。
  
Exchange Online を使用して Microsoft Teams Rooms を展開するには、次の手順に従います。 関連するコマンドレットを実行する適切なアクセス許可があることを確認します。 

   > [!NOTE]
   >  このセクションで説明されている [「Windows PowerShell コマンドレット用の Azure Active Directory モジュール](/powershell/azure/active-directory/overview)」 (たとえば  Set-MsolUser)  は、Microsoft Teams Rooms デバイスのアカウントを設定するためにテストされました。 他のコマンドレットでも機能することがありますが、この特定のシナリオではテストされていません。

Active Directory フェデレーションサービス (AD FS) を展開した場合は、次の手順を実行する前に、ユーザーアカウントを管理されているユーザーに変換し、この手順を実行した後にユーザーをフェデレーションユーザーに戻す必要があります。
  
### <a name="create-an-account-and-set-exchange-properties"></a>アカウントを作成して、Exchange のプロパティを設定する

1. PC でリモートの Windows PowerShell セッションを開始し、次のように Exchange Online に接続します。

    ``` Powershell
   Import-Module ExchangeOnlineManagement
   Connect-ExchangeOnline
    ```

2. セッションを確立したら、新しいメールボックスを作成して、それを RoomMailboxAccount として有効にするか、既存の会議室メールボックスの設定を変更します。 これにより、アカウントは、Microsoft Teams Roomsに認証されます。

   既存のリソースメールボックスを変更する場合：

   ``` Powershell
   Set-Mailbox -Identity 'ConferenceRoom01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

    新しいリソース メールボックスを作成している場合:

   ``` Powershell
   New-Mailbox -MicrosoftOnlineServicesID 'ConferenceRoom01@contoso.com' -Alias ConferenceRoom01 -Name "Conference Room 01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

3. 会議のエクスペリエンスを改善するには、ユーザー アカウントで、次のように Exchangeプロパティを設定する必要があります。

   ``` Powershell
   Set-CalendarProcessing -Identity 'ConferenceRoom01@contoso.com' -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity 'ConferenceRoom01@contoso.com' -AddAdditionalResponse $true -AdditionalResponse "This is a Microsoft Teams Meeting room!"
   ```

### <a name="add-an-email-address-for-your-on-premises-domain-account"></a>オンプレミスのドメインアカウントのメールアドレスを追加する

1. **Active Directory UsersおよびComputers AD** ツールで、コンテナーまたMicrosoft Teams Rooms のアカウントの作成先となる組織単位を右クリックし、**新規** そして **ユーザー** の順にクリックします。
2. 前のコマンドレット(Set-MailboxまたはNew-Mailbox)の表示名 (- Identity )を **フルネーム** ボックスに入力し、次にアリアスを **ユーザーログイン名** ボックスに入力します。 **[次へ]** をクリックします。
3. このアカウントのパスワードを入力します。確認のためにもう一度入力する必要があります。[**パスワードを無期限にする**] チェック ボックスだけがオンになっていることを確認します。

    > [!NOTE]
    > [**パスワードを無期限にする**] を選択すること は、Microsoft Teams Rooms 上で Skype for Business Serverを使用する要件です。  有効期限が切れないパスワードは、ドメインのルールで禁止されるかもしれません。 その場合は、Microsoft Teams Rooms のユーザーアカウントごとに例外を作成する必要があります。
  
4. [ **完了**] をクリックしてアカウントを作成します。
5. アカウントを作成したら、ディレクトリの同期を実行します。 これを行うには、PowerShell で[Set-MsolDirSyncConfiguration](/powershell/module/msonline/set-msoldirsyncconfiguration)を使用します。 それが完了したら、[ユーザー] ページに移動し、前の手順で作成した 2 つのアカウントがマージされていることを確認します。

### <a name="assign-a-microsoft-365-or-office-365-license"></a>Microsoft 365 または Office 365 ライセンスを割り当てる

1. 最初にAzure AD に接続して、アカウント設定をいくつか適用する必要があります。 このコマンドレットを実行して接続できます。 Active Directory の詳細については、[Azure ActiveDirectory (MSOnline) 1.0](/powershell/azure/active-directory/overview)を参照してください。

   > [!NOTE]
   > [Azure Active Directory PowerShell 2.0](/powershell/azure/active-directory/overview) はサポートされていません。

    ``` PowerShell
   Connect-MsolService
    ```
  <!--   ``` Powershell
     Connect-AzureAD -Credential $cred
     ``` -->

2. ユーザー アカウントが動作するには、有効なMicrosoft 365またはOffice 365ライセンスが必要Exchangeがあります。 ライセンスを所有している場合は、使用場所をユーザーアカウントに割り当てる必要があります。これにより、アカウントに使用できるライセンス SKU が決まります。 課題は次の手順で行います。
3. 次に、`Get-MsolAccountSku`を使用します。  <!--Get-AzureADSubscribedSku--> Microsoft 365 または Office 365の 組織で使用でき SKU の一覧を取得します。
4. ライセンスを追加するには、 `Set-MsolUserLicense` <!-- Set-AzureADUserLicense--> することができます。 この場合、Microsoft Teams Rooms Standard ライセンスが適用されています。 

    ```PowerShell
    Set-MsolUser -UserPrincipalName 'ConferenceRoom01@contoso.com' -UsageLocation 'US'
    Get-MsolAccountSku
    Set-MsolUserLicense -UserPrincipalName 'ConferenceRoom01@contoso.com' -AddLicenses "contoso:MEETING_ROOM"
    ```
  <!--   ``` Powershell
     Set-AzureADUserLicense -UserPrincipalName 'PROJECT01@contoso.com' -UsageLocation 'US'
     Get-AzureADSubscribedSku
     Set-AzureADUserLicense -UserPrincipalName 'PROJECT01@contoso.com' -AddLicenses $strLicense
     ``` -->

## <a name="related-topics"></a>関連トピック

[Microsoft Teams Rooms のアカウントを構成する](rooms-configure-accounts.md)

[Microsoft Teams Rooms を計画する](rooms-plan.md)
  
[Microsoft Teams Rooms をデプロイする](rooms-deploy.md)
  
[Microsoft Teams Rooms コンソールを構成する](console.md)
  
[Microsoft Teams Rooms を管理する](rooms-manage.md)
