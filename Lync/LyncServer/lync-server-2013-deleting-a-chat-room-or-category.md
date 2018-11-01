---
title: 'Lync Server 2013: チャット ルームまたはカテゴリの削除'
TOCTitle: チャット ルームまたはカテゴリの削除
ms:assetid: adccb869-0015-4eba-ac73-718bac7843b5
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ215881(v=OCS.15)
ms:contentKeyID: 48273258
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 でのチャット ルームまたはカテゴリの削除

 

_**トピックの最終更新日:** 2012-11-01_

常設チャット ルームは削除できます。使用しなくなったチャット ルームは、無効にすることができます。詳細については、「[Lync Server 2013 でのチャット ルームの無効化または有効化](lync-server-2013-disabling-or-enabling-a-chat-room.md)」を参照してください。

常設チャット管理者は、無効になったチャット ルームを照会し、 Windows PowerShell のコマンドレット **Remove-CsPersistentChatRoom** を使用することにより、チャット ルームを定期的に削除して完全に削除することができます。

カテゴリは削除できます。ただし、カテゴリを削除するには、最初にその下のチャット ルームをすべて削除するか、削除する空のカテゴリを残してチャット ルームを新しいカテゴリに移動する必要があります。 常設チャット サーバーでは、チャット ルームが含まれるカテゴリを削除することができません。詳細については、「[Lync Server 2013 での 1 つのカテゴリから他のカテゴリへのチャット ルームの移動](lync-server-2013-moving-a-chat-room-from-one-category-to-another.md)」を参照してください。

Windows PowerShell コマンドライン インターフェイスを使用した空のカテゴリの削除の詳細については、「[Windows PowerShell コマンドレットを使用した常設チャット サーバーの構成](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md)」の「ルーム管理」を参照してください。

チャット ルームおよびカテゴリの詳細については、「展開」のドキュメントの「[Lync Server 2013 でルームを構成する](lync-server-2013-configure-rooms.md)」および「[Lync Server 2013 でのカテゴリの構成](lync-server-2013-configure-categories.md)」を参照してください。

