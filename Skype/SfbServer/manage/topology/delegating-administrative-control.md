---
title: ビジネス サーバーの Skype の管理制御を委任します。
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: ''
ms.openlocfilehash: 64d1b33c7ee41c028d3af7454a131f67de2c9146
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30890066"
---
# <a name="delegate-administrative-control-of-skype-for-business-server"></a>ビジネス サーバーの Skype の管理制御を委任します。 

ビジネス サーバーの Skype は、管理タスクは、役割ベースのアクセス制御 (RBAC) 機能を使用してユーザーに委任します。 ビジネス サーバーの Skype をインストールするときの RBAC の役割の多くが作成されます。 これらの役割は、Active Directory ドメイン サービスのユニバーサル セキュリティ グループに対応します。 などの CsHelpDesk の RBAC の役割は、Active Directory ドメイン サービス内の Users コンテナー内の CsHelpDesk グループに対応します。 さらに、各 RBAC の役割は、Skype のビジネス サーバーの Windows PowerShell コマンドレットのセットに関連付けられています。 これらのコマンドレットは、特定の RBAC の役割が割り当てられているユーザーによって実行できるタスクを表します。 などのロック ・ CsClientPin、UnlockCsClientPin コマンドレットは、CsHelpDesk の役割を割り当てられています。 つまり、CsHelpDesk の役割が割り当てられているユーザーをロックし、ユーザーの暗証番号 (pin) 番号のロックを解除します。 ただし、CsHelpDesk の役割では新規 CsVoicePolicy コマンドレットを割り当てられていませんが。 つまり、CsHelpDesk の役割が割り当てられているユーザーが新しい音声ポリシーを作成できません。

## <a name="viewing-information-about-rbac-roles"></a>RBAC の役割に関する情報を表示します。

ビジネス サーバー管理シェルには、Skype 内で次のコマンドを実行することによって、RBAC の役割に関する基本的な情報を取得できます。

`Get-CsAdminRole`

RBAC の役割 (たとえば、CsVoiceAdministrator) の Id は、Active Directory ドメイン サービス内の Users コンテナーにセキュリティ グループに直接マッピングを持っていることに留意してください。

ロールに割り当てられているコマンドレットの一覧を表示するのには次のようなコマンドを使用します。

`Get-CsAdminRole -Identity "CsHelpDesk" | Select-Object -ExpandProperty Cmdlets`

## <a name="assigning-an-rbac-role-to-a-user"></a>RBAC の役割をユーザーに割り当てる

RBAC の役割をユーザーに割り当てるには、適切な Active Directory セキュリティ グループにそのユーザーを追加する必要があります。 たとえば、CsLocationAdministrator ロールをユーザーに割り当てるには、CsLocationAdministrator グループにそのユーザーを追加する必要があります。 行うには、次の手順を実行します。

1. アクセス許可を持つアカウントを使用して、Active Directory グループのメンバーシップを変更、Active Directory ユーザーとコンピューターがインストールされているコンピューターにログオンします。
2. [**スタート**] ボタン**すべてのプログラム** **[管理ツール**] をクリックして、 **Active Directory ユーザーとコンピューター**] をクリックします。
3. Active Directory ユーザーとコンピューターでは、コンピューターのドメイン名を展開を **[Users** ] コンテナーをクリックします。
4. **CsLocationAdministrator**、セキュリティ グループを右クリックし、[**プロパティ**] をクリックします。
5. **プロパティ**] ダイアログ ボックスの [**メンバー** ] タブで [**追加**] をクリックします。
6. **[ユーザー、コンピューター、連絡先、またはグループ**] ダイアログ ボックスで、ユーザー名を入力またはグループ (たとえば、Ken Myer)**を選択するオブジェクト名を入力してください**] ボックスに追加するユーザーの名前を表示でし、[ **OK**] をクリックします。
7. **プロパティ**] ダイアログ ボックスで [ **OK**を] をクリックします。

RBAC の役割が割り当てられていることを確認するには、Get CsAdminRoleAssignment コマンドレットは、ユーザーの SamAccountName (Active Directory のログオン名) をコマンドレットに渡すことを使用します。 たとえば、ビジネス サーバー管理シェルには、Skype 内からは、このコマンドを実行します。

`Get-CsAdminRoleAssignment  -Identity "kenmyer"`
