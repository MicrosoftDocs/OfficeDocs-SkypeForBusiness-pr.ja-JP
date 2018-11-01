---
title: 'Lync Server 2013: 新しいチャット ルームの作成または編集'
TOCTitle: 新しいチャット ルームの作成または編集
ms:assetid: aa8f4349-cfd9-4036-9c4d-de8fb2c4c8a4
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ215880(v=OCS.15)
ms:contentKeyID: 48273218
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 での新しいチャット ルームの作成または編集

 

_**トピックの最終更新日:** 2015-03-19_

常設チャット ルームの構成は一般的にユーザーが行い、通常、 常設チャット管理者がチャット ルームの構成または管理を行うことはありません。チャット ルームを管理するための Windows PowerShell コマンドレットを使用できるのは、 **CsPersistentChatAdministrator** 管理者のみです。

特定のカテゴリで **作成者**となっているユーザーは、 Lync クライアントを使用してチャット ルームを作成および管理することができます。特定のチャット ルームのマネージャーとして指定されているユーザーは、ルームのプロパティまたはメンバーシップの編集など、チャット ルームの継続的な管理を実行することもできます。


> [!TIP]
> 常設チャット管理者は作成者でもある場合があり、作成者に課された制限の対象にはなりません。



常設チャット管理者の場合、オプションで、 Windows PowerShell コマンドレットを使用する代わりにチャット ルームを作成および管理するユーザー インターフェイスを使用することもできます。このためには、 常設チャット サーバーの管理者の SIP を有効にしてから、 Lync クライアントを使用してチャット ルームを作成および管理します。

ユーザーに対してカスタムのチャット ルーム管理ワークフローを作成する場合、 常設チャット サーバー構成の **RoomManagementUrl** プロパティを設定すると、ユーザーを Lync クライアントからカスタム ソリューションにリダイレクトすることができます。

Windows PowerShell コマンドライン インターフェイスを使用したチャット ルームの構成の詳細については、「[Windows PowerShell コマンドレットを使用した常設チャット サーバーの構成](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md)」の「ルーム管理」を参照してください。

チャット ルームの構成の詳細については、「展開」のドキュメントの「[Lync Server 2013 でルームを構成する](lync-server-2013-configure-rooms.md)」を参照してください。

