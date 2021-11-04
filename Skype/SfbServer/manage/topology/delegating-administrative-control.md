---
title: サーバーの管理制御を委任Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: ''
ms.openlocfilehash: 1ee1cdce6bae163ea51ebb73ac9b536e75b204a8
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/04/2021
ms.locfileid: "60743423"
---
# <a name="delegate-administrative-control-of-skype-for-business-server"></a>サーバーの管理制御を委任Skype for Business Server 

このSkype for Business Server管理タスクは、役割ベースのアクセス制御 (RBAC) 機能を使用してユーザーに委任されます。 アプリケーションをインストールSkype for Business Server、多数の RBAC ロールが作成されます。 これらの役割は、Active Directory ドメイン サービスのユニバーサル セキュリティ グループに対応します。 たとえば、RBAC ロール CsHelpDesk は、Active Directory ドメイン サービスの Users コンテナーにある CsHelpDesk グループに対応しています。 さらに、各 RBAC 役割は、複数のコマンドレットのセットSkype for Business ServerWindows PowerShellされます。   これらのコマンドレットは、特定の RBAC ロールが割り当てられているユーザーが実行できるタスクを表します。 たとえば、CsHelpDesk の役割には、管理者および UnlockCsClientPin コマンドレットLock-CsClientPin割り当て済みです。 つまり、CsHelpDesk ロールが割り当てられているユーザーは、ユーザーの PIN 番号をロックおよびロック解除できます。 ただし、CsHelpDesk の役割には、このコマンドレットが割りNew-CsVoicePolicy付けられていない。 つまり、CsHelpDesk ロールが割り当てられているユーザーは、新しい音声ポリシーを作成できません。

## <a name="viewing-information-about-rbac-roles"></a>RBAC の役割に関する情報の表示

RBAC の役割に関する基本情報を取得するには、次のコマンドを管理シェルSkype for Business Server実行します。

`Get-CsAdminRole`

RBAC ロールの ID (たとえば、CsVoiceAdministrator) には、Active Directory ドメイン サービスの Users コンテナーにあるセキュリティ グループへの直接マッピングがあります。

役割に割り当てられているコマンドレットのリストを表示するには、次のようなコマンドを使用してください。

`Get-CsAdminRole -Identity "CsHelpDesk" | Select-Object -ExpandProperty Cmdlets`

## <a name="assigning-an-rbac-role-to-a-user"></a>RBAC ロールをユーザーに割り当てる

RBAC ロールをユーザーに割り当てるには、そのユーザーを適切な Active Directory セキュリティ グループに追加する必要があります。 たとえば、CsLocationAdministrator 役割をユーザーに割り当てるには、そのユーザーを CsLocationAdministrator グループに追加する必要があります。 ユーザーをセキュリティ グループに追加するには、次の手順を実行します。

1. Active Directory グループのメンバーシップを変更できるアクセス許可を持つアカウントを使用して、Active Directory ユーザーおよびコンピューターがインストールされているコンピューターにログオンします。
2. [**スタート**] をクリックし、[**すべてのプログラム**] をクリックし、[**管理ツール**] をクリックし、[**Active Directory ユーザーおよびコンピューター**] をクリックします。
3. Active Directory ユーザーおよびコンピューターで、自分のドメインの名前を展開し、[**Users**] コンテナーをクリックします。
4. セキュリティ グループの [**CsLocationAdministrator**] を右クリックし、[**プロパティ**] をクリックします。
5. [**プロパティ**] ダイアログ ボックスの [**メンバー**] タブで、[**追加**] をクリックします。
6. [ユーザー **、** コンピューター、連絡先、またはグループの選択] ダイアログ ボックスで、[選択するオブジェクト名を入力する] ボックスにグループに追加するユーザーのユーザー名または表示名(Ken Myer など) を入力し **、[OK]** をクリックします。
7. [**プロパティ**] ダイアログ ボックスで [**OK**] をクリックします。

RBAC の役割が割り当てられていることを確認するには、Get-CsAdminRoleAssignment コマンドレットを使用して、ユーザーの SamAccountName (Active Directory ログオン名) コマンドレットを渡します。 たとえば、管理シェル内から次のコマンドSkype for Business Server実行します。

`Get-CsAdminRoleAssignment  -Identity "kenmyer"`
