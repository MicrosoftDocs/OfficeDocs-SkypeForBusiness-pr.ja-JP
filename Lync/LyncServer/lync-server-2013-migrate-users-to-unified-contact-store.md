---
title: 'Lync Server 2013: 統合連絡先ストアへのユーザーの移行'
TOCTitle: 統合連絡先ストアへのユーザーの移行
ms:assetid: 215a8ec1-d63e-4fdf-b73d-75aeb9dddb43
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ204737(v=OCS.15)
ms:contentKeyID: 48271485
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 での統合連絡先ストアへのユーザーの移行

 

_**トピックの最終更新日:** 2012-10-15_

ユーザーの連絡先は、次の場合に Exchange 2013 サーバーに自動的に移行されます。

  - UcsAllowed が True に設定されたユーザー サービス ポリシーがユーザーに割り当てられている場合。

  - ユーザーに Exchange 2013 メールボックスがプロビジョニングされており、ユーザーがそのメールボックスに最低 1 回サインインしている場合。

  - ユーザーが Lync 2013 リッチ クライアントを使用してログインした場合。

ユーザーが Lync 2010 またはそれ以前のクライアントを使用してログインした場合、あるいはユーザーが Exchange 2013 サーバーに接続していない場合は、ユーザー サービス ポリシーが無視されて、ユーザーの連絡先は Lync Server にとどまります。

ユーザーの連絡先が移行されているかどうかは、次のどちらかの方法で確認できます。

  - クライアント コンピューターで次のレジストリ キーを調べます。
    
    HKEY\_CURRENT\_USER\\Software\\Microsoft\\Office\\15.0\\Lync\\\<SIP URL\>\\UCS
    
    ユーザーの連絡先が Exchange 2013 に保管されている場合、このキーには値が 2165 に設定された InUCSMode という値が含まれます。

  - **Test-CsUnifiedContactStore** コマンドレットを実行します。Lync Server 管理シェルのコマンドラインで、次のように入力します。
    
        Test-CsUnifiedContactStore -UserSipAddress "sip:kenmyer@litwareinc.com" -TargetFqdn "atl-cs-001.litwareinc.com"
    
    **Test-CsUnifiedContactStore** が成功した場合は、ユーザーの連絡先が統合連絡先ストアに移行されています。

