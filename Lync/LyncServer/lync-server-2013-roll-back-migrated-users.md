---
title: 'Lync Server 2013: 移行したユーザーのロールバック'
TOCTitle: 移行したユーザーのロールバック
ms:assetid: bfabaf0b-9a42-4057-b729-a7ab9eee8c72
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ205224(v=OCS.15)
ms:contentKeyID: 48273436
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 での移行したユーザーのロールバック

 

_**トピックの最終更新日:** 2012-10-07_

統合連絡先ストア機能をロールバックする必要がある場合、そのユーザーを Exchange 2010 または Lync Server 2010 に戻す場合にのみ連絡先をロールバックできます。ロールバックするには、ユーザーに対するポリシーを無効にしてから **Invoke-CsUcsRollback** コマンドレットを実行します。 **Invoke-CsUcsRollback** を実行するだけでは永続的なロールバックを確実に行うには不十分です。これは、ポリシーを無効化しない場合、統合連絡先ストアの移行が再び開始されるためです。たとえば、 Exchange 2013 が Exchange 2010 にロールバックされたためにユーザーがロールバックされ、さらにユーザーのメールボックスが Exchange 2013 に移動された場合、ユーザーのサービス ポリシーでそのユーザーに対して統合連絡先ストアが有効になっている限り、統合連絡先ストアの移行がロールバックの 7 日後に再び開始されます。


> [!IMPORTANT]
> <STRONG>Move-CsUser</STRONG> コマンドレットを実行すると、次の場合に、ユーザーの連絡先ストアが Exchange 2013 から Lync Server 2013 に自動的にロールバックされます。 
> <UL>
> <LI>
> <P>ユーザーが Lync Server 2013 から Lync Server 2010 移動されている場合。</P>
> <LI>
> <P>ユーザーが設置の境界を越えて移行されている場合。たとえば、ユーザーが Skype for Business Online から Lync Server 2013 の設置に移動された場合や、その逆の場合。</P></LI></UL>




> [!IMPORTANT]
> バックアップ データベースから統合連絡先ストアをインポートするときに、統合連絡先ストアのモードがエクスポートとインポートの間で変更されると、統合連絡先ストアのデータとユーザー データが破損する可能性があります。たとえば次のような例が挙げられます。 
> <UL>
> <LI>
> <P>ユーザーの連絡先を Exchange 2013 に移行する前に連絡先リストをエクスポートし、移行後に同じデータをインポートした場合、統合連絡先ストアのデータと連絡先リストが破損します。</P>
> <LI>
> <P>ユーザーを Exchange 2013 に移行した後でユーザー データをエクスポートし、移行をロールバックした後で、何らかの理由で移行後のデータをインポートした場合、統合連絡先ストアのデータと連絡先リストが破損します。</P></LI></UL>




> [!IMPORTANT]
> Exchange のメールボックスを Exchange 2013 から Exchange 2010 に移動する前に、 Exchange 管理者は Lync Server 管理者に対し、まず Lync Server ユーザーの連絡先を Exchange 2013 から Lync Server にロールバックするように確認する必要があります。統合連絡先ストアの連絡先を Lync Server にロールバックするには、このセクションで後述する「統合連絡先ストアの連絡先を Exchange 2013 から Lync Server 2013 にロールバックするには」の手順を参照してください。



次の手順では、ユーザーの連絡先をロールバックする方法を説明します。 **Move-CsUser** コマンドレットを使用して Lync Server 2013 と Lync Server 2010 の間でユーザーを移動する場合は、ユーザーを Lync Server 2013 から Lync Server 2010 に移動するときに **Move-CsUser** コマンドレットによって統合連絡先ストアが自動的にロールバックされるので、この手順を省略できます。 **Move-CsUser** では、統合連絡先ストアのポリシーは無効化されないので、ユーザーが Lync Server 2013 に戻された場合は統合連絡先ストアの移行が繰り返されます。

## ユーザーの連絡先を Lync Server 2013 から Lync Server 2010 へロールバックするには

1.  Lync Server 管理シェルを以下の手順で起動します。\[**スタート**\]、\[**すべてのプログラム**\]、\[**Microsoft Lync Server 2013**\]、\[**Lync Server 管理シェル**\] の順にクリックします。

2.  ロールバック後にユーザーの再移行が行われないように、ロールバックするユーザーに対して統合連絡先ストアを無効にします (この手順は、将来ユーザーが再移行されないようにしたい場合にだけ実行します)。統合連絡先ストアを個別のユーザーに対して無効にするには、コマンドラインで、次のように入力します。
    
        Set-CsUserServicesPolicy -Identity "<policy name>" -UcsAllowed $False
    
    次に例を示します。
    
        Set-CsUserServicesPolicy -Identity "UCS Enabled Users" -UcsAllowed $False

3.  ユーザーを Lync Server 2013 から Lync Server 2010 へ移動する前に、指定した Lync Server のユーザーのバディ リストをロールバックします。
    

    > [!IMPORTANT]
    > このステップを省略すると、バディ リストが失われます。



4.  指定したユーザーをロールバックします。コマンドラインで、次のように入力します。
    
        Invoke-CsUcsRollback -Identity "<user display name>"
    
    次に例を示します。
    
        Invoke-CsUcsRollback -Identity "Ken Myer"
    

    > [!IMPORTANT]
    > –Force オプションを使用して強制的にロールバックすることはお勧めしません。このオプションを使用すると、ユーザーの連絡先が失われます。



## 統合連絡先ストアの連絡先を Exchange 2013 から Lync Server 2013 にロールバックするには

1.  Lync Server 管理シェルを以下の手順で起動します。\[**スタート**\]、\[**すべてのプログラム**\]、\[**Microsoft Lync Server 2013**\]、\[**Lync Server 管理シェル**\] の順にクリックします。

2.  ロールバック後にユーザーの再移行が行われないように、ロールバックするユーザーに対して統合連絡先ストアを無効にします。統合連絡先ストアを個別のユーザーに対して無効にするには、コマンドラインで、次のように入力します。
    
        Set-CsUserServicesPolicy -Identity "<policy name>" -UcsAllowed $False
    
    次に例を示します。
    
        Set-CsUserServicesPolicy -Identity "UCS Enabled Users" -UcsAllowed $False

3.  指定したユーザーをロールバックします。コマンドラインで、次のように入力します。
    
        Invoke-CsUcsRollback -Identity "<user display name>"
    
    次に例を示します。
    
        Invoke-CsUcsRollback -Identity "Ken Myer"
    

    > [!IMPORTANT]
    > まず Lync Server ユーザーをロールバックしてから、 Exchange 2013 のメールボックスを移動する必要があります。 Lync Server のロールバックが完了するまで、Exchange 管理者は Exchange をロールバックできません。–Force オプションを使用して強制的にロールバックすることはお勧めしません。このオプションを使用すると、ユーザーの連絡先が失われます。



4.  ユーザーを Lync Server にロールバックした後は、Exchange 管理者は Exchange ユーザーを Exchange 2013 から Exchange 2010 にロールバックできます。

