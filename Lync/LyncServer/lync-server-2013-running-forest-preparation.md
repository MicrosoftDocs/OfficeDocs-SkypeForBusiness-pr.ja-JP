---
title: 'Lync Server 2013: フォレストの準備の実行'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Running forest preparation
ms:assetid: 9d62f7be-bcfe-421d-8d8a-225567102a35
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412732(v=OCS.15)
ms:contentKeyID: 48184991
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 129926afe17f946a2ea32d7c67fdea89fab32a54
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41732818"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="running-forest-preparation-for-lync-server-2013"></a>Lync Server 2013 でのフォレストの準備の実行

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-29_

セットアップまたは Lync Server 管理シェルコマンドレットを使用して、フォレストを準備することができます。 フォレストを準備するコマンドレットでは、 **CsAdForest を有効**にします。

フォレストを準備したら、ドメインの準備を実行する前に、グローバル設定がレプリケートされていることを確認する必要があります。

<div>

## <a name="to-use-setup-to-prepare-the-forest"></a>セットアップを使用してフォレストを準備するには

1.  フォレストルートドメインの Enterprise Admins グループのメンバーとしてドメインに参加しているコンピューターにログオンします。

2.  Lync Server 2013 インストールフォルダーまたはメディアから setup.exe を実行して、展開ウィザードを開始します。

3.  [**Active Directory の準備**] をクリックして、展開状態が判別されるまで待ちます。

4.  **手順 3: 現在のフォレストを準備**するには、[**実行**] をクリックします。

5.  [**フォレストの準備**] ページで、[**次へ**] をクリックします。
    
    <div>
    

    > [!NOTE]  
    > フォレストの準備 Lync Server 2013 のユニバーサルグループを配置する場所を選ぶことができます。 組織の要件と一致する配置先を選択してください。

    
    </div>

6.  [**コマンドを実行しています**] ページで [**タスク状態: 完了**] を見つけて、[**ログの表示**] をクリックします。

7.  [**アクション**] 列で、[**フォレスト**の準備] を展開し、各タスクの最後で** \<成功\> **の実行結果を探して、フォレストの準備が正常に完了したことを確認します。次に、[**完了**] をクリックします。

8.  Active Directory のレプリケーションが完了するまで待機するか、フォレストルートドメインコントローラーの**Active Directory サイトとサービス**スナップインに記載されているすべてのドメインコントローラーに対して強制的にレプリケーションを実行してから、ドメインの準備を実行します。 すべての Active Directory サイトのドメインコントローラー間で強制的にレプリケーションを実行して、サイト内での複製が分単位で行われるようにします。

</div>

<div>

## <a name="to-use-cmdlets-to-prepare-the-forest"></a>コマンドレットを使用してフォレストを準備するには

1.  フォレストルートドメインの Domain Admins グループのメンバーとしてドメインに参加しているコンピューターにログオンします。

2.  Lync Server のコアコンポーネントは、次のようにインストールします。
    
    1.  Lync Server 2013 のインストールフォルダーまたはメディアから setup.exe を実行して、Lync Server 展開ウィザードを開始します。
    
    2.  Microsoft Visual C++ 再頒布可能パッケージをインストールするかどうかを確認するメッセージが表示されたら、[**はい**] をクリックします。
    
    3.  [Lync Server 2013 セットアップ] ダイアログボックスで、Lync Server ファイルをインストールする場所を入力するように求められます。 既定の場所を選ぶか、目的の場所を**参照**し、[**インストール**] をクリックします。
    
    4.  [使用許諾契約] ページで、[**使用許諾契約書に同意**します] をオンにし、[ **OK]** をクリックします。 インストーラーは、Lync Server 2013 コアコンポーネントをインストールします。

3.  Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。

4.  次のコマンドレットを実行します。
    
        Enable-CsAdForest [-GroupDomain <FQDN of the domain in which to create the universal groups>]
    
    次に例を示します。
    
        Enable-CsAdForest -GroupDomain domain1.contoso.com 
    
    GroupDomain パラメーターを指定しない場合、既定値はローカルドメインです。 ユニバーサルグループが、既定のドメインではないドメインで以前に作成された場合は、GroupDomain パラメーターを明示的に指定する必要があります。

5.  Active Directory のレプリケーションが完了するまで待機するか、フォレストルートドメインコントローラーの**Active Directory サイトとサービス**スナップインに記載されているすべてのドメインコントローラーに対して強制的にレプリケーションを実行してから、ドメインの準備を実行します。

6.  フォレストの準備が正常に完了したことを確認します。 次のコマンドレットを実行します。
    
        Get-CsAdForest 
    
    フォレストの準備が正常に完了した場合、このコマンドレットは**\_LC FORESTSETTINGS\_STATE\_** の値を返します。

</div>

<div>

## <a name="see-also"></a>関連項目


[コマンドレットの使用による Lync Server 2013 のフォレストの準備のリバース](lync-server-2013-using-cmdlets-to-reverse-forest-preparation.md)  


[Lync Server 2013 でのフォレストの準備](lync-server-2013-preparing-the-forest.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

