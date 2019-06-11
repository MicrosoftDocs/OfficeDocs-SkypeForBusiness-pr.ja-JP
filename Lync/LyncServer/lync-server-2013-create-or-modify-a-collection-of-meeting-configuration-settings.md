---
title: 会議の構成設定のコレクションを作成または変更する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create or modify a collection of meeting configuration settings
ms:assetid: ce6773c1-a0d5-4405-8e32-33a6f3a46a1a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721889(v=OCS.15)
ms:contentKeyID: 49733822
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2b948d5aded2447e5319378a613fdf474c3e5450
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833814"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-collection-of-meeting-configuration-settings-in-lync-server-2013"></a>Lync Server 2013 で会議の構成設定のコレクションを作成または変更する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-02-23_

[会議の設定] ページの設定を使用して、会議の参加エクスペリエンスのさまざまな特性を定義できます。 既定では、グローバル設定によって結合操作が定義されます。 サイトレベルとプールレベルの会議の参加設定を作成することもできます。 プール レベル設定を作成すると、その設定は、そのプールがホストするすべての会議に適用されます。 プール レベル設定を作成しない場合は、サイト レベル設定が存在すればそれが適用されます。 サイト レベル設定を定義しない場合は、グローバル設定がすべての会議に適用されます。

<div>

## <a name="to-create-new-meeting-join-settings"></a>新しい会議の参加設定を作成するには

1.  CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。 Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。

3.  左側のナビゲーションバーで、[**会議**] をクリックし、[**会議の設定**] をクリックします。

4.  [**会議の構成**] ページで、[**新規作成**] をクリックし、次のいずれかを実行します。
    
      - サイト レベルのポリシーを作成するには、[**サイト構成**] をクリックします。[**サイトの選択**] 検索フィールドに、会議参加設定を定義するサイトの名前の全体または一部を入力します。サイトの結果一覧で対象のサイトをクリックして、[**OK**] をクリックします。
    
      - プール レベルのポリシーを作成するには、[**プール構成**] をクリックします。[**サービスの選択**] 検索フィールドに、会議参加設定を定義するプール サービスの名前の全体または一部を入力します。サービスの結果一覧で、対象のプールをクリックして [**OK**] をクリックします。

5.  公衆交換電話網 (PSTN) からダイヤルインする参加者をロビーを介してルーティングするには、[**PSTN 発信者はロビーをバイパスする**] チェック ボックスをオフにします。既定では、PSTN からダイヤルインした参加者は会議に直接移動します。

6.  会議の発表者になることができるユーザーを構成するには、[**発表者として指定**] で、次のいずれかの操作を実行します。
    
      - 開催者以外のユーザーが発表者になることを許可しない場合は、[**なし**] をクリックします。
    
      - 組織のメンバーになっている参加者にのみ発表者になることを許可する場合は、[**会社**] をクリックします。これは既定の設定です。
    
      - 参加者すべてに発表者になることを許可する場合は、[**全員**] をクリックします。

7.  開催者が会議のスケジュール時に会議の種類を選択できるようにするには、[**既定で割り当てられた会議の種類**] チェック ボックスをオフにします。既定では、会議の種類が自動的に割り当てられます。

8.  匿名 (未認証) ユーザーが自動的に承認されないようにするには、[**既定で匿名ユーザーを承認する**] チェック ボックスをオフにします。既定では、匿名ユーザーは会議に対して自動的に承認されます。

9.  参加者に送られる会議の招待をカスタマイズするには、以下を行います。 URL およびカスタム フッター テキストの長さは最大 1 KB です。 [**ヘルプ URL**] 以外は、カスタムの値を指定しない場合、会議に含まれません。 ユーザー設定のヘルプ URL が含まれていない場合は、Lync の既定のヘルプ URL が招待状に表示されます。
    
      - 会議の招待に表示されるロゴをカスタマイズするには、[**ロゴ URL**] にロゴの場所を入力します。
        
        <div>
        

        > [!NOTE]
        > ロゴは、サイズが 188 x 30 ピクセルの GIF または JPG 画像である必要があります。

        
        </div>
    
      - 会議招待に表示されるヘルプ テキストをカスタマイズするには、[**ヘルプ URL**] にヘルプ テキストの場所を入力します。
    
      - 会議の招待に表示される法的情報をカスタマイズするには、[**リーガル テキスト URL**] にリーガル テキストの場所を入力します。
    
      - 会議の招待に表示されるカスタム フッター テキストをカスタマイズするには、[**カスタム フッターのテキスト**] にテキストを入力します。

10. [**確定**] をクリックします。

</div>

<div>

## <a name="to-modify-an-existing-collection-of-meeting-configurations"></a>会議の構成の既存のコレクションを変更するには

1.  CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。 Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。

3.  左側のナビゲーションバーで、[**会議**] をクリックし、[**会議の設定**] をクリックします。

4.  会議構成の一覧で、変更する構成をクリックし、[**編集**] をクリックして、[**詳細の表示**] をクリックします。

5.  [**会議の構成の編集**] で、構成名以外の構成設定を変更します (構成名は変更不可です)。

6.  [**コミット**] をクリックします。

</div>

<div>

## <a name="creating-new-meeting-configuration-settings-by-using-windows-powershell-cmdlets"></a>Windows PowerShell コマンドレットを使用して新しい会議構成設定を作成する

会議の構成設定は、Windows PowerShell と新しい-Csmeeting 構成コマンドレットを使用して、(サイトのスコープのみで) 作成できます。 このコマンドレットは、Lync Server 2013 管理シェルから、または Windows PowerShell のリモートセッションから実行できます。 リモートの Windows PowerShell を使用して Lync Server に接続する方法の詳細については、「Lync Server Windows PowerShell のブログ記事」を参照してください[http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。「リモート PowerShell を使用して Microsoft Lync Server 2010 を管理する」を参照してください。

<div>

## <a name="to-create-meeting-configuration-settings-that-use-the-default-values"></a>既定値を使用する会議の構成設定を作成するには

  - このコマンドは、Redmond サイトの会議構成設定の新しいセットを作成します。
    
        New-CsMeetingConfiguration -Identity "site:Redmond"
    
    上記のコマンドでは必須の Identity パラメーター以外のパラメーターは指定されていないため、新しい会議構成設定はすべてのプロパティについて既定値を使用します。

</div>

<div>

## <a name="to-change-a-property-value-when-creating-meeting-configuration-settings"></a>会議の構成設定を作成するときにプロパティの値を変更するには

  - 異なるプロパティ値を使用する設定を作成するには、適切なパラメーターとパラメーター値を指定します。たとえば、会議の全員が発表者となることを既定で許可する会議構成設定のセットを作成するには、次のようなコマンドを使用します。
    
        New-CsMeetingConfiguration -Identity "site:Redmond" -DesignateAsPresenter "Everyone"

</div>

<div>

## <a name="to-change-multiple-property-values-when-creating-meeting-configuration-settings"></a>会議の構成設定を作成するときに複数のプロパティの値を変更するには

  - 複数のパラメーターを含めることにより複数のプロパティ値を変更できます。 たとえば、次のコマンドは、発表者として会議に対して全員を管理し、その会議に対して正式に許可されるまでは、ロビーでも PSTN ユーザーによる待機を強制します。
    
        New-CsMeetingConfiguration -Identity "site:Redmond" -DesignateAsPresenter "Everyone" -PSTNUCallersBypassLobby $True

</div>

詳細については、「[新しい-Cs会議構成](https://technet.microsoft.com/en-us/library/Gg398065(v=OCS.15))」コマンドレットのヘルプトピックを参照してください。

</div>

</div>

<span> </span>

</div>

</div>

</div>

