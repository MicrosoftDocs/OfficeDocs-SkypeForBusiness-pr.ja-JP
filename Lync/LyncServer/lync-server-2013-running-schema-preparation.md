---
title: 'Lync Server 2013: スキーマの準備の実行'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Running schema preparation
ms:assetid: 9d02bdb1-ff29-417a-bcce-b068b31207d8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412729(v=OCS.15)
ms:contentKeyID: 48184911
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4b743e5ef93b14279f5f2f16cb70241617a0c8f0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822539"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="running-active-directory-schema-preparation-in-lync-server-2013"></a>Lync Server 2013 での Active Directory スキーマの準備の実行

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-29_

セットアップまたは Lync Server 管理シェルコマンドレットを使用して、Active Directory スキーマを準備することができます。 Active Directory スキーマを拡張するコマンドレットは、**インストール-CsAdServerSchema**です。

<div>


> [!NOTE]  
> スキーマ準備コマンドレット (<STRONG>Install: CsAdServerSchema</STRONG>) では、スキーママスターにアクセスする必要があります。これには、リモートレジストリサービスが実行されており、リモートレジストリキーが有効になっている必要があります。 スキーママスターでリモートレジストリサービスを有効にできない場合は、スキーママスターでコマンドレットをローカルで実行できます。 レジストリのリモートアクセスの詳細については、Microsoft サポート技術情報の記事314837「レジストリへのリモートアクセスを管理<A href="http://go.microsoft.com/fwlink/p/?linkid=125769">http://go.microsoft.com/fwlink/p/?linkId=125769</A>する方法」を参照してください。



</div>

スキーマの準備が完了したら、フォレストの準備に進む前に、スキーマパーティションがレプリケートされていることを手動で確認します。 詳細については、「 [Lync Server 2013 での Active Directory スキーマのレプリケーションを確認](lync-server-2013-verifying-schema-replication.md)する」を参照してください。

<div>

## <a name="to-use-setup-to-prepare-the-schema-of-the-current-forest"></a>セットアップを使用して現在のフォレストのスキーマを準備するには

1.  Schema Admins グループのメンバーとして、またはスキーママスターの管理者権限を持つ、フォレスト内のサーバーにログオンします。

2.  Lync Server 2013 インストールフォルダーまたはメディアから setup.exe を実行して、展開ウィザードを開始します。

3.  Microsoft Visual C++ 再頒布可能パッケージをインストールするかどうかを確認するメッセージが表示されたら、[**はい**] をクリックします。

4.  [Lync Server 2013 セットアップ] ダイアログボックスで、Lync Server ファイルをインストールする場所を入力するように求められます。 既定の場所を選ぶか、目的の場所を**参照**し、[**インストール**] をクリックします。

5.  [使用許諾契約] ページで、[**使用許諾契約書に同意**します] をオンにし、[ **OK]** をクリックします。

6.  インストーラーによって Lync Server のコアコンポーネントがインストールされます。

7.  展開ウィザードの準備ができたら、[ **Active Directory の準備**] をクリックし、展開の状態が決定されるまで待ちます。

8.  **手順 1: スキーマを準備**して、[**実行**] をクリックします。

9.  [**スキーマの準備**] ページで、[**次へ**] をクリックします。

10. [**コマンドの実行**] ページで [**タスク状態: 完了**] を見つけて、[**ログの表示**] をクリックします。

11. [**アクション**] 列で、[**スキーマの準備**] を展開し、各タスクの最後で** \<成功\> **の実行結果を確認して、スキーマの準備が正常に完了したことを確認します。次に、[**完了**] をクリックします。

12. Active Directory のレプリケーションが完了するまで待つか、レプリケーションを強制的に実行します。

13. スキーマの変更が他のすべてのドメインコントローラーにレプリケートされていることを手動で確認します。 詳細については、「 [Lync Server 2013 での Active Directory スキーマのレプリケーションを確認](lync-server-2013-verifying-schema-replication.md)する」を参照してください。

</div>

<div>

## <a name="to-use-cmdlets-to-prepare-the-schema-of-the-current-forest"></a>コマンドレットを使用して現在のフォレストのスキーマを準備するには

1.  フォレスト内のコンピューターに Schema Admins グループのメンバーとしてログオンし、スキーママスターの管理者権限を持つコンピューターにログオンします。

2.  Lync Server のコアコンポーネントは、次のようにインストールします。
    
    1.  Lync Server 2013 のインストールフォルダーまたはメディアから setup.exe を実行して、Lync Server 展開ウィザードを開始します。
    
    2.  Microsoft Visual C++ 再頒布可能パッケージをインストールするかどうかを確認するメッセージが表示されたら、[**はい**] をクリックします。
    
    3.  [Lync Server 2013 セットアップ] ダイアログボックスで、Lync Server ファイルをインストールする場所を入力するように求められます。 既定の場所を選ぶか、目的の場所を**参照**し、[**インストール**] をクリックします。
    
    4.  [使用許諾契約] ページで、[**使用許諾契約書に同意**します] をオンにし、[ **OK]** をクリックします。 インストーラーは、Lync Server 2013 コアコンポーネントをインストールします。

3.  Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。

4.  次のコマンドレットを実行します。
    
        Install-CsAdServerSchema [-Ldf <directory where the .ldf file is located>] 
    
    Ldf パラメーターを指定しない場合、既定値は、レジストリから読み取った Lync Server 2013 インストールパスです。
    
    次に例を示します。
    
        Install-CsAdServerSchema -Ldf "C:\Program Files\Microsoft Lync Server 2013\Deployment\Setup"

5.  次のコマンドレットを使用して、スキーマの準備が完了するのを確認します。
    
        Get-CsAdServerSchema 
    
    スキーマ**\_の\_\_** 準備が正常に完了した場合、このコマンドレットは、スキーマのバージョンの現在の値を返します。

6.  Active Directory のレプリケーションが完了するまで待つか、レプリケーションを強制的に実行します。

7.  スキーマの変更が他のすべてのドメインコントローラーにレプリケートされていることを手動で確認します。 詳細については、「 [Lync Server 2013 での Active Directory スキーマのレプリケーションを確認](lync-server-2013-verifying-schema-replication.md)する」を参照してください。

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 での Active Directory スキーマのレプリケーションの確認](lync-server-2013-verifying-schema-replication.md)  


[Lync Server 2013 での Active Directory スキーマの準備](lync-server-2013-preparing-the-active-directory-schema.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

