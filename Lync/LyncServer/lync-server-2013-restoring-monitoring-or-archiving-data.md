---
title: 'Lync Server 2013: 監視またはアーカイブデータを復元する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Restoring monitoring or archiving data
ms:assetid: 60118526-13bb-4b03-803e-6ffae219d436
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202175(v=OCS.15)
ms:contentKeyID: 51541483
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9621fe3c1905dbd34fd3b4da39b2562c608d6355
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733167"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="restoring-monitoring-or-archiving-data-in-lync-server-2013"></a>Lync Server 2013 での監視またはアーカイブデータの復元

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-02-18_

障害が発生した後に Lync Server を起動して実行するために、データの監視とアーカイブを復元する必要はありません。 ただし、データの監視とアーカイブが組織にとって重要である場合は、データベースを再作成した後でデータを復元する必要があります。

次の手順では、SQL Server Management Studio を使用して、アーカイブまたはモニタリングデータを復元する方法について説明します。

<div>

## <a name="to-restore-monitoring-or-archiving-data-from-a-backup-file"></a>バックアップファイルからのデータの監視またはアーカイブを復元するには

1.  ローカルコンピューターの管理者グループのメンバー、または同等のユーザー権限を持つグループとして、復元するサーバーにログオンします。

2.  SQL Server Management Studio を開きます。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **microsoft sql server 2012** ]、または [ **microsoft sql server 2008 R2**] をクリックして、[ **sql server management studio**] をクリックします。

3.  [**サーバーへの接続**] で、少なくともサーバーの名前と認証情報を指定して、SQL Server インスタンスに接続します。

4.  **オブジェクトエクスプローラー**で、[**データベース**] を右クリックし、[**データベースの復元**] をクリックします。

5.  [**ページの選択**] の [**全般**] をクリックし、[**データベース**] でデータベース名を次のように選択します。
    
      - アーカイブデータベースの場合は、 **Lcslog**を選択します。
    
      - 通話の詳細記録 (CDR) データベースの場合は、[ **Lcscdr**] を選びます。
    
      - Quality of Experience (QoE) データベースの場合は、[ **QoEMetrics**] を選びます。

6.  [**デバイスから] を**クリックします。

7.  [**復元するバックアップセットの選択**] でバックアップファイルをクリックし、[**復元**] をクリックします。

8.  [**ページの選択**] の [**オプション**] をクリックし、データファイルのパスとログのパスが正しいフォルダーにあることを確認して、[ **OK]** をクリックします。

</div>

<div>

## <a name="to-make-sure-that-access-control-lists-acls-are-correct"></a>アクセス制御リスト (Acl) が正しく設定されていることを確認するには

1.  [**データベース**] を展開し、[アーカイブ] または [監視] データベースを展開し、[**セキュリティ**] を展開して、[**ユーザー**] を展開します。

2.  ドメイングループ RTCComponentUniversalServices がユーザーとして存在することを確認します。

3.  [**ユーザー**] の下に RTCComponentUniversalServices が存在しない場合は、次の操作を行います。
    
    1.  [**ユーザー**] を右クリックし、[**新しいユーザー**] をクリックします。
    
    2.  [ **Login name**] に、不足しているグループ名 RTCComponentUniversalServices を入力します。
    
    3.  [**データベースロールメンバーシップ**] で、[ **ServerRole** ] 権限を選び、[ **OK]** をクリックします。
    
    <div>
    

    > [!NOTE]  
    > アーカイブまたは監視サービスを再起動する必要はありません。

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

