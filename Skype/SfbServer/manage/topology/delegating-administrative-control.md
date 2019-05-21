---
title: Skype for Business Server の管理制御を委任する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: ''
ms.openlocfilehash: 1775fc4f02b7efa9ec26b962154f0aa90b59b296
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34279208"
---
# <a name="delegate-administrative-control-of-skype-for-business-server"></a>Skype for Business Server の管理制御を委任する 

Skype for Business Server では、管理タスクは、役割ベースのアクセス制御 (RBAC) 機能を使用してユーザーに委任されます。 Skype for Business Server をインストールすると、複数の RBAC の役割が作成されます。 これらの役割は、Active Directory ドメイン サービスのユニバーサル セキュリティ グループに対応します。 たとえば、RBAC の役割 CsHelpDesk は、Active Directory ドメインサービスの Users コンテナーに含まれる CsHelpDesk グループに対応しています。 さらに、各 RBAC の役割は、Skype for Business Server Windows PowerShell コマンドレットのセットと関連付けられています。 これらのコマンドレットは、特定の RBAC の役割が割り当てられたユーザーが実行できるタスクを表します。 たとえば、CsHelpDesk role には、Lock と UnlockCsClientPin コマンドレットが割り当てられています。 つまり、CsHelpDesk の役割が割り当てられているユーザーは、ユーザーの PIN 番号のロックとロック解除を行うことができます。 ただし、CsHelpDesk の役割には、CsVoicePolicy コマンドレットが割り当てられていません。 つまり、CsHelpDesk role を割り当てられているユーザーは、新しいボイスポリシーを作成することはできません。

## <a name="viewing-information-about-rbac-roles"></a>RBAC ロールに関する情報を表示する

次のコマンドを Skype for Business Server 管理シェルから実行して、RBAC ロールに関する基本的な情報を取得できます。

`Get-CsAdminRole`

RBAC の役割 (CsVoiceAdministrator など) の Id は、Active Directory ドメインサービスの Users コンテナーにあるセキュリティグループに直接マッピングされていることに注意してください。

ロールに割り当てられているコマンドレットの一覧を表示するには、次のようなコマンドを使用します。

`Get-CsAdminRole -Identity "CsHelpDesk" | Select-Object -ExpandProperty Cmdlets`

## <a name="assigning-an-rbac-role-to-a-user"></a>RBAC の役割をユーザーに割り当てる

RBAC の役割をユーザーに割り当てるには、適切な Active Directory セキュリティグループにそのユーザーを追加する必要があります。 たとえば、CsLocationAdministrator の役割をユーザーに割り当てるには、そのユーザーを CsLocationAdministrator グループに追加する必要があります。 そのためには、次の手順を実行します。

1. Active Directory グループのメンバーシップを変更する権限を持つアカウントを使用して、Active Directory ユーザーとコンピューターがインストールされているコンピューターにログオンします。
2. [**スタート**] をクリックし、[**すべてのプログラム**] をクリックし、[**管理ツール**] をクリックして、[ **Active Directory ユーザーとコンピューター**] をクリックします。
3. Active Directory ユーザーとコンピューターで、ドメインの名前を展開し、[**ユーザー** ] コンテナーをクリックします。
4. セキュリティグループ**Cslocationadministrator 者**を右クリックし、[**プロパティ**] をクリックします。
5. [**プロパティ**] ダイアログボックスの [**メンバー** ] タブで、[**追加**] をクリックします。
6. **[ユーザー、コンピューター、連絡先、またはグループの選択**] ダイアログボックスで、 **[選択するオブジェクト名を入力**してください] ボックスに、グループに追加するユーザー名またはユーザー名 (Ken Myer など) を入力し、[ **OK]** をクリックします。
7. [**プロパティ**] ダイアログボックスで、[ **OK]** をクリックします。

RBAC の役割が割り当てられていることを確認するには、ユーザーの "SamAccountName (Active Directory のログオン名)" というコマンドレットを渡して、Csadminadminroleassignment コマンドレットを使います。 たとえば、次のコマンドを Skype for Business Server 管理シェル内から実行します。

`Get-CsAdminRoleAssignment  -Identity "kenmyer"`
