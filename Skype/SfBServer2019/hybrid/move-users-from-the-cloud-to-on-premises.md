---
title: 移動ユーザーが社内のクラウドに
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
ms.custom: ''
description: Skype からの社内のビジネス オンラインへのユーザーを移動する方法について説明します。
ms.openlocfilehash: 7032e7f2968b7861a7fac199fd8ba949980fe770
ms.sourcegitcommit: f091c351bec56219a8c91b8c12b9c1f5c5983c95
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/25/2019
ms.locfileid: "29530944"
---
# <a name="move-users-from-the-cloud-to-on-premises"></a>移動ユーザーが社内のクラウドに 

必要な場合、戻すことができます、ユーザーが以前に移行から社内のクラウドに移行する (Skype を使用して、ビジネスをオンラインまたはチームのみ) かどうかを施設内にします。 移動するユーザーまたは TeamsOnly のビジネスのオンライン モードのいずれかの Skype から Skype の設置型展開ビジネス サーバーの設置型のツールは、両方とも、ビジネス サーバー コントロール パネルの移動 CsUser コマンドレット、または、Skype のいずれかを使用します。 設置型の展開に戻る、ユーザーを移動するときにユーザーを移動するには、どのプールを決める必要があります。

> [!Important]
> TeamsOnly モードで、ユーザーが以前にあったと CU8 のビジネス サーバー 2015 の Skype より以前のバージョンを使用している場合、そのユーザーの TeamsUpgradePolicy の TeamsOnly のモードの割り当ても削除しなければなりません。 オンプレミス ユーザーはモード = TeamsOnly。  ビジネス サーバーの Skype の以降のバージョンは、この割り当てを自動的に削除します。 詳細については、[補助金 CsTeamsUpgradePolicy](https://docs.microsoft.com/en-us/powershell/module/skype/grant-csteamsupgradepolicy)を参照してください。

## <a name="prerequisites"></a>前提条件

- 組織では、Azure AD 接続が正しく構成されている必要があり、[構成の Azure AD 接続](configure-azure-ad-connect.md)の説明に従って、ユーザーのすべての関連属性が同期します。
- 移動中のユーザーにオンライン バックアップからの社内は、オンプレミスの Active Directory に存在していなければなりません。
- [ビジネスのハイブリッド構成の Skype](configure-federation-with-skype-for-business-online.md)の説明に従って、Skype のビジネスのハイブリッドを構成しなければなりません。

## <a name="moving-users-back-to-on-premises"></a>移動ユーザーが社内にバックアップします。

移動すると、ユーザー、クラウドから戻る設置。

- ビジネス サーバー配置では、機能のため、Skype では、ユーザーが操作します。 
- ビジネス オンラインまたはチームのいずれかの Skype で存在していた取引先担当者は、ビジネスのサーバーを Skype に移行されます。 連絡先の 2 つのセットがマージされ、社内に移行されます。  さらに、チームで既存の連絡先は、チーム内に残ります。
- ユーザーには、チームが使用しても、ビジネス ユーザーは、Skype で相互運用することはありませんもになる、フェデレーション組織のユーザーと通信すること。
- ビジネス オンラインの Skype での会議では、自動的に移行*されません*に設置型の。 ユーザーがいずれかのスケジュールを変更、会議や、必要な場合は、[会議の移行ツール](https://support.office.com/en-us/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4)を使用します。

### <a name="move-users-with-move-csuser"></a>Csuser からの移動でユーザーの移動

Csuser からの移動を指定する場合は、オンプレミス Skype のビジネス管理シェルの PowerShell ウィンドウで実行できます。 [管理者の資格情報が必要な](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)の説明に従って、Office 365 テナントだけでなく、オンプレミス環境に十分な特権が必要です。 両方の環境で権限のある単一のアカウントを使用することができますか、または設置型の資格情報を持つビジネス サーバー管理シェル ウィンドウに、オンプレミス Skype を起動し、使用できます、 `-Credential` 、Office 365 の資格情報を指定するパラメーター必要な Office 365 管理者の役割を持つアカウント。

Csuser からの移動を使用して社内のユーザーを移動します。

- Id パラメーターを使用して移動するユーザーを指定します。
- 指定ターゲット パラメーターを指定するユーザーをホストする目的で設置型プールの完全修飾ドメイン名を持つ。
- 設置型および Office 365 の両方のための十分なアクセス許可を持つ 1 つのアカウントがないを使用して、Office 365 のための十分な権限を持つアカウントを指定するには、資格情報パラメーターです。
- Office 365 にアクセス許可を持つアカウントは、"on.microsoft.com"で終わっていない場合、は、[ために必要な管理者資格情報](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)で説明するよう、適切な値を持つ、- HostedMigrationOverrideUrl パラメーターを指定する必要があります。

次のコマンドレットのシーケンスは、Skype をビジネスのサーバーのユーザーを移動するために使用して、Office 365 の資格情報は別のアカウントであり、取得の資格情報のプロンプトへの入力として提供されたと仮定しています。

```
$cred=Get-Credential
$url="https://admin1a.online.lync.com/HostedMigration/hostedmigrationService.svc"
Move-CsUser -Identity username@contoso.com -Target pool.corp.contoso.com -Credential $cred -HostedMigrationOverrideUrl $url
```

### <a name="move-users-with-the-skype-for-business-server-control-panel"></a>ビジネス サーバーのコントロール パネルの Skype でユーザーを移動します。

1. ビジネス サーバー管理のため、Skype を開くパネルのアプリケーション。
2. 左側のナビゲーションでは、**ユーザー**を選択します。
3. 設置型に移動するには、ユーザーを検索するには、**検索**を使用します。
4. 、ユーザーを選択してから、**アクション**」ドロップ ダウン リストの上、クリックして**設置型を選択したユーザーを移動**します。
5. ウィザードでは、ユーザーをホストし、[**次へ**] をクリックするユーザーのプールを選択します。
6. メッセージが表示されたらにサインイン、Office 365 で終了するアカウントを使用しています。 onmicrosoft.com 十分なアクセス許可とします。
7. ユーザーを移動するのには**次へ**、し、[**次へ**1 つのより多くの時間をクリックします。
8. ウィザードではなく、メインのコントロール パネルの [アプリケーションの上部に成功または失敗に関連するステータス メッセージが提供されることに注意してください。

### <a name="removing-teamsonly-mode"></a>TeamsOnly モードを削除します。

CU8 を持つビジネス 2015年の Skype より前のバージョンを使用して、ユーザーに移動 TeamsOnly モードでの設置型の場合は、UpgradeToTeams のインスタンスを削除する必要があります`TeamsUpgradePolicy`の社内ユーザーを移動する前にします。 別のモードのポリシーを明示的に許可するかである限り、テナントのグローバル ポリシーは、UpgradeToTeams ではありません) は、グローバル ポリシーを使用するには、そのユーザーの既存のポリシーの割り当てを削除するだけです。

TeamsUpgradePolicy のユーザーの割り当てを削除するのには、Skype のビジネス オンライン PowerShell ウィンドウから次のコマンドレットを実行します。

`Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName $null`

または、TeamsUpgradePolicy の別のインスタンスを割り当てることがないモード = TeamsOnly、コマンドレットのグループのパラメーターの値として適切なインスタンスの名前を指定できます。 TeamsUpgradePolicy の使用可能なインスタンスの一覧を表示するには、Get CsTeamsUpgradePolicy を実行します。


## <a name="see-also"></a>関連項目

Move-CsUser
