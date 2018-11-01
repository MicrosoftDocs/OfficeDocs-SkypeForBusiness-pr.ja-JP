---
title: 'Lync Server 2013: 中央管理ストアのレプリケーションの状態'
TOCTitle: 中央管理ストアのレプリケーションの状態
ms:assetid: f514f88d-986b-4e45-b79b-e04a7616c1fe
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Dn720926(v=OCS.15)
ms:contentKeyID: 62246652
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 での中央管理ストアのレプリケーションの状態

 

_**トピックの最終更新日:** 2015-01-26_

管理者が Lync Server に何らかの種類の変更を加えた場合 (たとえば、管理者が新しい音声ポリシーを作成した場合や、アドレス帳サーバーの構成設定を変更した場合)、その変更は中央管理ストアに記録されます。 その後、Lync Server のサービスまたはサーバーの役割を実行しているすべてのコンピューターに、その変更をレプリケートする必要があります。

データをレプリケートするために、(中央管理サーバー上で動作している) マスター レプリケーターは、変更後の構成データのスナップショットを作成します。その後、Lync Server のサービスまたはサーバーの役割を実行している各コンピューターに対して、このスナップショットのコピーが送信されます。それらのコンピューター上では、レプリケーション エージェントがスナップショットを受信し、変更後のデータをアップロードします。次に、エージェントは、マスター レプリケーターに、レプリケーションの最新の状態を報告するメッセージを送信します。

Get-CsManagementStoreReplicationStatus コマンドレットを使用して、組織内の一部 (またはすべて) の Lync Server コンピューターのレプリケーションの状態を確認できます。

このコマンドレットを実行できるユーザー: 既定では、次のグループのメンバーが、Get-CsManagementStoreReplicationStatus コマンドレットのローカル実行を承認されています。RTCUniversalUserAdmins、RTCUniversalServerAdmins。

このコマンドレットが割り当てられているすべての RBAC の役割 (自分で作成したカスタムの RBAC の役割を含む) の一覧を取得するには、Windows PowerShell プロンプトから以下のコマンドを実行します。

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Get-CsManagementStoreReplicationStatus"}

## 関連項目

#### その他のリソース

[Get-CsManagementStoreReplicationStatus](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsManagementStoreReplicationStatus)

