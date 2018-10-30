---
title: 'Lync Server 2013: Enhanced 9-1-1 (E9-1-1) と仲介サーバー'
TOCTitle: Enhanced 9-1-1 (E9-1-1) と仲介サーバー
ms:assetid: d231221f-5596-4a87-a463-269f5bcce65f
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg398903(v=OCS.15)
ms:contentKeyID: 48273652
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 の Enhanced 9-1-1 (E9-1-1) と仲介サーバー

 

_**トピックの最終更新日:** 2012-09-29_

仲介サーバーの機能が拡張され、Enhanced 9-1-1 (E9-1-1) サービス プロバイダーと適切に対話できるようになりました。 仲介サーバーを特別に構成する必要はありません。E9-1-1 の対話に必要な SIP 拡張は、仲介サーバーとゲートウェイ ピア (E9-1-1 サービス プロバイダーを含むインターネット テレフォニー サービス プロバイダーの PSTN ゲートウェイ、IP-PBX、または SBC) の対話のために、仲介サーバーの SIP プロトコルに標準実装されています。

E9-1-1 SBC が仲介サーバー プールと対話できるかどうかによって、E9-1-1 サービス プロバイダーへの SIP トランクを既存の仲介サーバー プールで終了できるか、あるいはスタンドアロン仲介サーバーが必要になるかが決まります。詳細については、「[Lync Server 2013 の M:N トランク](lync-server-2013-m-n-trunk.md)」を参照してください。

