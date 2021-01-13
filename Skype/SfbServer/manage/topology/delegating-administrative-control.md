---
title: Skype for Business Server の管理制御を委任する
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: ''
ms.openlocfilehash: eb78fc7e0f831bae1c5dd6e207791e27aa4c68d1
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832797"
---
# <a name="delegate-administrative-control-of-skype-for-business-server"></a>Skype for Business Server の管理制御を委任する 

Skype for Business Server では、管理タスクは役割ベースのアクセス制御 (RBAC) 機能を使用してユーザーに委任されます。 Skype for Business Server をインストールすると、多くの RBAC の役割が作成されます。 これらの役割は、Active Directory ドメイン サービスのユニバーサル セキュリティ グループに対応しています。 たとえば、RBAC の役割 CsHelpDesk は、Active Directory ドメイン サービスの Users コンテナーにある CsHelpDesk グループに対応します。 さらに、各 RBAC の役割は、一連の Skype for Business Server Windows PowerShellされます。 これらのコマンドレットは、特定の RBAC の役割が割り当てられているユーザーが実行できるタスクを表します。 たとえば、CsHelpDesk の役割には、Lock-CsClientPin UnlockCsClientPin コマンドレットが割り当てされています。 つまり、CsHelpDesk の役割が割り当てられているユーザーは、ユーザーの PIN 番号をロックおよびロック解除できます。 ただし、CsHelpDesk の役割にこのコマンドレットが割りNew-CsVoicePolicyされていない。 つまり、CsHelpDesk の役割が割り当てられているユーザーは、新しい音声ポリシーを作成できません。

## <a name="viewing-information-about-rbac-roles"></a>RBAC の役割に関する情報の表示

Rbac の役割に関する基本情報を取得するには、Skype for Business Server 管理シェルから次のコマンドを実行します。

`Get-CsAdminRole`

RBAC の役割の IDENTITY (CsVoiceAdministrator など) は、Active Directory ドメイン サービスの Users コンテナーにあるセキュリティ グループに直接マッピングされます。

役割に割り当てられているコマンドレットのリストを表示するには、次のようなコマンドを使用してください。

`Get-CsAdminRole -Identity "CsHelpDesk" | Select-Object -ExpandProperty Cmdlets`

## <a name="assigning-an-rbac-role-to-a-user"></a>RBAC の役割をユーザーに割り当てる

RBAC の役割をユーザーに割り当てるには、そのユーザーを適切な Active Directory セキュリティ グループに追加する必要があります。 たとえば、CsLocationAdministrator 役割をユーザーに割り当てるには、そのユーザーを CsLocationAdministrator グループに追加する必要があります。 ユーザーをセキュリティ グループに追加するには、次の手順を実行します。

1. Active Directory グループのメンバーシップを変更できるアクセス許可を持つアカウントを使用して、Active Directory ユーザーおよびコンピューターがインストールされているコンピューターにログオンします。
2. [**スタート**] をクリックし、[**すべてのプログラム**] をクリックし、[**管理ツール**] をクリックし、[**Active Directory ユーザーおよびコンピューター**] をクリックします。
3. Active Directory ユーザーおよびコンピューターで、自分のドメインの名前を展開し、[**Users**] コンテナーをクリックします。
4. セキュリティ グループの [**CsLocationAdministrator**] を右クリックし、[**プロパティ**] をクリックします。
5. [**プロパティ**] ダイアログ ボックスの [**メンバー**] タブで、[**追加**] をクリックします。
6. [ユーザー  、コンピューター、連絡先、またはグループの選択] ダイアログ ボックスで、グループに追加するユーザーのユーザー名または表示名 (Ken Myer など) を[選択するオブジェクト名を入力してください] ボックスに入力し **、[OK]** をクリックします。
7. [**プロパティ**] ダイアログ ボックスで [**OK**] をクリックします。

RBAC の役割が割り当てられていることを確認するには、Get-CsAdminRoleAssignment コマンドレットを使用して、ユーザーの SamAccountName (Active Directory ログオン名) コマンドレットを渡します。 たとえば、Skype for Business Server 管理シェル内から次のコマンドを実行します。

`Get-CsAdminRoleAssignment  -Identity "kenmyer"`
