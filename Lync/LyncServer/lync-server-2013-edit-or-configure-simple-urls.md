---
title: 'Lync Server 2013: 簡単な URL の編集または構成'
TOCTitle: 簡単な URL の編集または構成
ms:assetid: 0008aeea-4ae9-4e36-83cd-ef7ff7b6e128
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg398063(v=OCS.15)
ms:contentKeyID: 48271051
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 での簡単な URL の編集または構成

 

_**トピックの最終更新日:** 2014-02-04_

この手順では、ローカル管理者または特権が割り当てられたドメイン グループのメンバーシップは必要ありません。標準ユーザーとしてコンピューターにログオンする必要があります。

Lync Server 2013 では、簡易 URL を使用して、内線発信と外線発信を フロント エンド サーバー または ディレクター (展開されている場合) 上のサービスに振り分けます。簡易 URL の詳細については、「計画」のドキュメントの「[Lync Server 2013 での簡単な URL の計画](lync-server-2013-planning-for-simple-urls.md)」を参照してください。簡易 URL は複数のオプションから選ぶことができます。これらのオプションの詳細については、「計画」のドキュメントの「[Lync Server 2013 の簡易 URL の DNS 要件](lync-server-2013-dns-requirements-for-simple-urls.md)」を参照してください。

既定では、簡易 URL (たとえば、Dial-in の簡易 URL) は次の形式で構成されます: https://dialin.\<SIP domain\>

## 簡易 URL を構成するには

1.  トポロジ ビルダー で、\[ **Lync Server**\] ノードを右クリックし、\[ **プロパティの編集** \] をクリックします。

2.  \[ **簡易 URL** \] ウィンドウで、編集する \[ **電話アクセスの URL:** \] (Dial-in) または \[ **会議の URL:** \] (Meet) のいずれかを選び、\[ **URL の編集** \] をクリックします。

3.  URL を目的の値に更新し、\[ **OK** \] をクリックして編集した URL を保存します。ここに示す例では、Dial-in URL を https://pool01.contoso.net/dialin に変更しています。

4.  必要に応じて、同じ手順を使用して Meet URL を編集します。

## オプションの管理用の簡易 URL を定義するには

1.  トポロジ ビルダー で、\[ **Lync Server**\] ノードを右クリックし、\[ **プロパティの編集** \] をクリックします。

2.  \[**管理アクセスの URL**\] ボックスに、Lync Server 2013 コントロール パネルへの管理アクセスに必要な簡易 URL を入力し、\[**OK**\] をクリックします。
    

    > [!TIP]
    > 管理 URL にできるだけ簡易 URL を使用することをお勧めします。最も簡単なのは、<STRONG>https://admin.</STRONG> <EM>&lt;domain&gt;</EM> です。

    

    > [!IMPORTANT]
    > 最初の展開後に簡易 URL を変更する場合、簡易 URL のドメイン ネーム システム (DNS) レコードと証明書に影響する変更について注意する必要があります。変更が簡易 URL の基本部分に影響する場合は、DNS レコードと証明書も変更する必要があります。たとえば、https://lync.contoso.com/Meet を https://meet.contoso.com に変更すると、ベース URL が lync.contoso.com から meet.contoso.com に変更されるため、meet.contoso.com を参照するためには DNS レコードと証明書を変更する必要があります。 簡易 URL を https://lync.contoso.com/Meet から https://lync.contoso.com/Meetings に変更した場合は、lync.contoso.com のベース URL は同じであるため、DNS と証明書の変更は必要ありません。ただし、簡易 URL 名を変更する場合は常に、各 ディレクター と フロント エンド サーバー で <STRONG>Enable-CsComputer</STRONG> コマンドレットを実行して、変更を登録する必要があります。



## 関連項目

#### 概念

[Lync Server 2013 での簡単な URL の計画](lync-server-2013-planning-for-simple-urls.md)

