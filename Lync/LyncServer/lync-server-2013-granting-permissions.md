---
title: 'Lync Server 2013: アクセス許可の付与'
TOCTitle: アクセス許可の付与
ms:assetid: d1c9ea66-bd07-480e-99a0-011108f97e42
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg398901(v=OCS.15)
ms:contentKeyID: 48273653
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 でのアクセス許可の付与

 

_**トピックの最終更新日:** 2012-10-15_

セットアップでは、特定の Active Directory 組織単位 (OU) の RTCUniversalServerAdmins ユニバーサル グループにアクセス許可を付与できます。これにより、その OU の RTCUniversalServerAdmins グループのメンバーは、指定されたドメインで Lync Server 2013 をインストールできます。OU についてアクセス許可を付与する場合、以下のアクセス許可が付与されます。

  - 読み取り

  - 書き込み

  - ReadSPN

  - WriteSPN

管理では、指定された OU にアクセス許可を追加することができ、これによりフォレストの準備によって作成された RTC ユニバーサル グループのメンバーは、Domain Admins グループのメンバーでなくてもその OU にアクセスできます。指定された OU に追加されるアクセス許可は、 **Enable-CsAdDomain** コマンドレットによってコンピューターおよびユーザーの OU コンテナーに追加されるアクセス許可と同じです。

## このセクション中

  - [Lync Server 2013 でのセットアップ アクセス許可の付与](lync-server-2013-granting-setup-permissions.md)

  - [Lync Server 2013 での組織単位アクセス許可の付与](lync-server-2013-granting-organizational-unit-permissions.md)

