---
title: 'Lync Server 2013: Lync Server の管理機能の委任'
TOCTitle: Lync Server 2013 の管理機能の委任
ms:assetid: 0f378eff-8ef4-4c60-9fd2-67d7ee259ef8
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg520951(v=OCS.15)
ms:contentKeyID: 48271281
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 の管理機能の委任

 

_**トピックの最終更新日:** 2013-02-22_

Lync Server 2013 では、新しい役割ベースのアクセス制御 (RBAC) 機能を使用して、管理タスクがユーザーに委任されます。Lync Server をインストールするときに、いくつかの RBAC 役割が作成されます。これらの役割は、Active Directory ドメイン サービス のユニバーサル セキュリティ グループに対応します。たとえば、RBAC 役割の CsHelpDesk は、Active Directory ドメイン サービスの Users コンテナーにある CsHelpDesk グループに対応します。また、各 RBAC 役割は、一連の Lync ServerWindows PowerShell コマンドレットに関連付けられます。これらのコマンドレットは、特定の RBAC 役割を割り当てられているユーザーが実行できるタスクを表します。たとえば、CsHelpDesk 役割には Lock-CsClientPin および UnlockCsClientPin コマンドレットが割り当てられているので、CsHelpDesk 役割を割り当てられたユーザーはユーザー PIN 番号をロックおよびロック解除できることになります。また、CsHelpDesk 役割には New-CsVoicePolicy コマンドレットは割り当てられていません、したがって、CsHelpDesk 役割を割り当てられたユーザーは新しい音声ポリシーを作成できません。

## RBAC 役割に関する情報の表示

Lync Server 管理シェル内部から次のコマンドを実行することで、RBAC 役割に関する基本情報を取得できます。

    Get-CsAdminRole

RBAC 役割 (たとえば、CsVoiceAdministrator) の ID が、Active Directory ドメイン サービスの Users コンテナーにあるセキュリティ グループへ直接マッピングされている点に注意してください。

役割に割り当てられているコマンドレットのリストを表示するには、次のようなコマンドを使用してください。

    Get-CsAdminRole -Identity "CsHelpDesk" | Select-Object -ExpandProperty Cmdlets

## RBAC 役割のユーザーへの割り当て

RBAC 役割をユーザーに割り当てるには、そのユーザーを該当する Active Directory セキュリティ グループに追加する必要があります。たとえば、CsLocationAdministrator 役割をユーザーに割り当てるには、そのユーザーを CsLocationAdministrator グループに追加する必要があります。ユーザーをセキュリティ グループに追加するには、次の手順を実行します。

**ユーザーをセキュリティ グループに割り当てるには**

1.  Active Directory グループのメンバーシップを変更できるアクセス許可を持つアカウントを使用して、Active Directory ユーザーおよびコンピューターがインストールされているコンピューターにログオンします。

2.  \[**スタート**\] をクリックし、\[**すべてのプログラム**\] をクリックし、\[**管理ツール**\] をクリックし、\[**Active Directory ユーザーおよびコンピューター**\] をクリックします。

3.  Active Directory ユーザーおよびコンピューターで、自分のドメインの名前を展開し、\[**Users**\] コンテナーをクリックします。

4.  セキュリティ グループの \[**CsLocationAdministrator**\] を右クリックし、\[**プロパティ**\] をクリックします。

5.  \[**プロパティ**\] ダイアログ ボックスの \[**メンバー**\] タブで、\[**追加**\] をクリックします。

6.  \[**ユーザー、コンピューター、連絡先、またはグループの選択**\] ダイアログ ボックスの \[**選択するオブジェクト名を入力してください**\] ボックスにグループに追加するユーザーの名前または表示名 (たとえば、**Ken Myer** ) を入力して \[**OK**\] をクリックします。

7.  \[**プロパティ**\] ダイアログ ボックスで \[**OK**\] をクリックします。

RBAC 役割が割り当てられていることを確認するために、[Get-CsAdminRoleAssignment](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsAdminRoleAssignment) コマンドレットを使用します。コマンドレットに、ユーザーの SamAccountName (Active Directory ログオン名) を渡してください。 たとえば、Lync Server 管理シェルから、次のコマンドを実行します。

    Get-CsAdminRoleAssignment  -Identity "kenmyer"

