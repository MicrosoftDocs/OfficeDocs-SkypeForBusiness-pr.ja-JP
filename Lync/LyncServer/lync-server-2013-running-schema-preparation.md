---
title: 'Lync Server 2013: スキーマの準備の実行'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Running schema preparation
ms:assetid: 9d02bdb1-ff29-417a-bcce-b068b31207d8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412729(v=OCS.15)
ms:contentKeyID: 48184911
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 12dda05b36406e620c08abac494dceecc7d314d0
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42201133"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="running-active-directory-schema-preparation-in-lync-server-2013"></a>Lync Server 2013 での Active Directory スキーマの準備の実行

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-29_

セットアップまたは Lync Server 管理シェルコマンドレットを使用して、Active Directory スキーマを準備することができます。 Active Directory スキーマを拡張するコマンドレットは **Install-CsAdServerSchema** です。

<div>


> [!NOTE]  
> スキーマ準備コマンドレット (<STRONG>Install-CsAdServerSchema</STRONG>) はスキーママスターにアクセスする必要があります。これには、リモートレジストリサービスが実行されていて、リモートレジストリキーが有効になっている必要があります。 スキーママスターでリモートレジストリサービスを有効にできない場合は、スキーママスターでローカルにコマンドレットを実行できます。 レジストリのリモートアクセスの詳細については、Microsoft サポート技術情報の記事314837「レジストリへのリモートアクセスを管理<A href="https://go.microsoft.com/fwlink/p/?linkid=125769">https://go.microsoft.com/fwlink/p/?linkId=125769</A>する方法」を参照してください。



</div>

スキーマの準備が完了したら、スキーマ パーティションがレプリケートされたことを手動で確認してから、フォレストの準備に進んでください。 詳細については、「 [Lync Server 2013 での Active Directory スキーマレプリケーションの確認](lync-server-2013-verifying-schema-replication.md)」を参照してください。

<div>

## <a name="to-use-setup-to-prepare-the-schema-of-the-current-forest"></a>セットアップを使用して、現在のフォレストのスキーマを準備するには

1.  Schema Admins グループのメンバーとして、さらに、スキーマ マスターにおける管理者権限を使用して、フォレスト内のサーバーにログオンします。

2.  Lync Server 2013 インストールフォルダーまたはメディアから、setup.exe を実行して、展開ウィザードを開始します。

3.  Microsoft Visual C++ (再頒布可能) のインストールを要求するメッセージが表示されたら、**[はい]** をクリックします。

4.  [Lync Server 2013 セットアップ] ダイアログボックスで、Lync Server ファイルをインストールする場所を指定するように求められます。 既定の場所を選択するか、または好みの場所を **[参照]** で選択し、**[インストール]** をクリックします。

5.  [使用許諾契約書] ページで **[使用許諾契約書に同意します]** チェック ボックスをオンにし、**[OK]** をクリックします。

6.  インストーラーによって Lync Server コアコンポーネントがインストールされます。

7.  展開ウィザードの準備ができたら、[**Active Directory の準備**] をクリックし、展開状態が判別されるまで待機します。

8.  [**ステップ 1: スキーマの準備**] で、[**実行**] をクリックします。

9.  [**スキーマの準備**] ページで、[**次へ**] をクリックします。

10. [**コマンドの実行**] ページで [**タスク状態: 完了**] を見つけて、[**ログの表示**] をクリックします。

11. [**アクション**] 列で [**スキーマ**の準備] を展開し、各タスクの最後に** \<成功\> **した実行結果を探して、スキーマの準備が正常に完了したことを確認し、ログを閉じて、[**完了**] をクリックします。

12. Active Directory レプリケーションが完了するのを待機するか、レプリケーションを強制的に実行します。

13. スキーマの変更が他のすべてのドメイン コントローラーにレプリケートされたことを手動で確認します。 詳細については、「 [Lync Server 2013 での Active Directory スキーマレプリケーションの確認](lync-server-2013-verifying-schema-replication.md)」を参照してください。

</div>

<div>

## <a name="to-use-cmdlets-to-prepare-the-schema-of-the-current-forest"></a>コマンドレットを使用して現在のフォレストのスキーマを準備するには

1.  Schema Admins グループのメンバーとして、さらに、スキーマ マスターにおける管理者の権限を使用して、フォレスト内のコンピューターにログオンします。

2.  Lync Server コアコンポーネントを次のようにインストールします。
    
    1.  Lync Server 2013 のインストールフォルダーまたはメディアから、setup.exe を実行して Lync Server 展開ウィザードを起動します。
    
    2.  Microsoft Visual C++ (再頒布可能) のインストールを要求するメッセージが表示されたら、**[はい]** をクリックします。
    
    3.  [Lync Server 2013 セットアップ] ダイアログボックスで、Lync Server ファイルをインストールする場所を指定するように求められます。 既定の場所を選択するか、または好みの場所を **[参照]** で選択し、**[インストール]** をクリックします。
    
    4.  [使用許諾契約書] ページで **[使用許諾契約書に同意します]** チェック ボックスをオンにし、**[OK]** をクリックします。 インストーラーによって Lync Server 2013 のコアコンポーネントがインストールされます。

3.  Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。

4.  実行
    
        Install-CsAdServerSchema [-Ldf <directory where the .ldf file is located>] 
    
    Ldf パラメーターを指定しない場合、既定値は、レジストリから読み取った Lync Server 2013 のインストールパスになります。
    
    次に例を示します。
    
        Install-CsAdServerSchema -Ldf "C:\Program Files\Microsoft Lync Server 2013\Deployment\Setup"

5.  次のコマンドレットを使用し、スキーマの準備が完了したことを確認します。
    
        Get-CsAdServerSchema 
    
    スキーマの準備が成功した場合、このコマンドレットは**スキーマ\_\_バージョン状態\_の CURRENT**の値を返します。

6.  Active Directory レプリケーションが完了するのを待機するか、レプリケーションを強制的に実行します。

7.  スキーマの変更が他のすべてのドメイン コントローラーにレプリケートされたことを手動で確認します。 詳細については、「 [Lync Server 2013 での Active Directory スキーマレプリケーションの確認](lync-server-2013-verifying-schema-replication.md)」を参照してください。

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

