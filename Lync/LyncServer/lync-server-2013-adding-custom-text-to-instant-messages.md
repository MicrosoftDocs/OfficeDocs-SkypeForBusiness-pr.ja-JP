---
title: 'Lync Server 2013: インスタント メッセージへのユーザー設定テキストの追加'
TOCTitle: インスタント メッセージへのユーザー設定テキストの追加
ms:assetid: cabcc3ec-9d35-42ac-a403-e21b7d538c2c
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg398847(v=OCS.15)
ms:contentKeyID: 52056706
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 でのインスタント メッセージへのユーザー設定テキストの追加

 

_**トピックの最終更新日:** 2013-02-20_

**New-CSClientPolicy** または **Set-CSClientPolicy**Lync Server 管理シェル コマンドレットを IMWarning パラメーター付きで使用することで、すべての Lync 2013 のインスタント メッセージ (IM) の会話の冒頭に免責事項または警告を追加します。

以下の例のコマンドを実行すると、新しい IM 会話が開始されるときにはいつでも、\[会話\] ウィンドウの上部にセキュリティ アラームが追加されます。

    New-CsClientPolicy -Identity IMSecurityNotice -IMWarning 
    "Remember, security is everyone's responsibility. Keep it confidential."

この新しいポリシーをユーザーに割り当てるには、 **Grant-CSClientPolicy** を使用します。詳細については、「 Lync Server 管理シェル」のドキュメントの「 **New-CSClientPolicy**」と「 **Grant-CSClientPolicy**」を参照してください。

