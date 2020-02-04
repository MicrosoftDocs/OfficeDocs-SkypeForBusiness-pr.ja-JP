---
title: Lync Server 2013 のアクセシビリティ
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Accessibility for people with disabilities
ms:assetid: 29c35a47-2513-425c-8b6b-250786573171
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204754(v=OCS.15)
ms:contentKeyID: 48183681
ms.date: 01/15/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0b3830196baea942bcbdf2109b9a3a761083cd02
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730479"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="accessibility-in-lync-server-2013"></a>Lync Server 2013 のアクセシビリティ

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2014-10-09_

Microsoft は、すべてのユーザーが使用できるように製品とサービスをより簡単にするために取り組んでいます。 以下のセクションでは、障碍のある方にとって Lync Server 2013 のアクセシビリティを高めるのに役立つ機能、製品、サービスについて説明します。

<div>

## <a name="accessibility-features-of-lync-server-2013"></a>Lync Server 2013 のアクセシビリティ機能

Lync Server 2013 の次の機能を使用すると、障碍のある方にとってアクセシビリティの高い機能を実現できます。

  - ショートカットキー

  - 図の代替テキスト

また、Windows のアクセシビリティ機能とツールによっては、Lync Server ユーザーが障碍のある方が便利な場合があります。 Windows PowerShell のサイズと色を変更すると、Lync Server 管理シェルを使用するときのアクセシビリティオプションが提供されます。 Windows PowerShell のアクセシビリティオプションの詳細については、TechNet ライブラリの「Windows PowerShell 2.0 での[http://go.microsoft.com/fwlink/p/?linkId=98964](http://go.microsoft.com/fwlink/p/?linkid=98964)アクセシビリティ」を参照してください。

</div>

<span id="BKMK_KeyboardShortcuts"></span>

<div>

## <a name="keyboard-shortcuts"></a>ショートカットキー

キーボードショートカットを使用して、Lync Server 管理ツールやその他の機能のユーザーインターフェイスを操作することができます。

キーボードショートカットを使用すると、次の一般的なタスクをすばやく実行できます。


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>目的</th>
<th>使用するショートカットキー</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>ユーザーインターフェイスで要素を切り替える。</p></td>
<td><p>見出し</p></td>
</tr>
<tr class="even">
<td><p>選択した要素のアクションを実行します。たとえば、[<strong>すべて表示</strong>]、[<strong>すべて表示</strong>しない]、[ハイパーリンクを開く] などです。</p></td>
<td><p>ください</p></td>
</tr>
<tr class="odd">
<td><p>選択した要素を、ページまたはメニューの次の要素に変更します。</p></td>
<td><p>見出し</p></td>
</tr>
<tr class="even">
<td><p>選択した要素をページの前の要素に変更します。</p></td>
<td><p>Shift + Tab</p></td>
</tr>
<tr class="odd">
<td><p>ページまたはメニュー上の選択した要素を上下左右に変更します。</p></td>
<td><p>方向キー</p></td>
</tr>
<tr class="even">
<td><p>ツリーで選んだノードを展開します。</p></td>
<td><p>+キー</p></td>
</tr>
<tr class="odd">
<td><p>ツリーで選んだノードを折りたたみます。</p></td>
<td><p>-キー</p></td>
</tr>
<tr class="even">
<td><p>メニューバーにアクセスする。</p></td>
<td><p>Del</p></td>
</tr>
<tr class="odd">
<td><p>メニューバーコマンドにアクセスする。</p></td>
<td><p>Alt + ショートカットメニューの下線付き文字</p></td>
</tr>
<tr class="even">
<td><p>証明書ウィザードでドロップダウンリストを選択します。</p></td>
<td><p>見出し</p></td>
</tr>
<tr class="odd">
<td><p>証明書ウィザードでドロップダウンリストを開きます。</p></td>
<td><p>Ctrl + Space</p></td>
</tr>
<tr class="even">
<td><p>証明書ウィザードのドロップダウンリストで、項目を強調表示します。</p></td>
<td><p>Tab キーを押し、Ctrl キーを押しながら方向キーを押して項目間を移動します。</p></td>
</tr>
<tr class="odd">
<td><p>証明書ウィザードのドロップダウンリストで、アイテムを選択または選択解除します。</p></td>
<td><p>Ctrl + Space</p></td>
</tr>
</tbody>
</table>


</div>

<span id="BKMK_AltText"></span>

<div>

## <a name="alternate-text-for-figures"></a>図の代替テキスト

Lync Server 2013 ヘルプのすべての図 (スクリーンショット、図、フローチャート、その他の図など) には、代替テキストが関連付けられています。 図の表示が困難なユーザーは、図のカーソルを一時停止して代替テキストを読み上げることができます。 代替テキストは、図に示されている内容を説明します。

</div>

<span id="BKMK_AccessMS"></span>

<div>

## <a name="accessibility-products-and-services-from-microsoft"></a>Microsoft のアクセシビリティ製品とサービス

以下のセクションでは、障碍のあるユーザーが Windows を使いやすくするための機能、製品、サービスについて説明します。

<div>


> [!NOTE]  
> このセクションの情報は、米国で Microsoft 製品をライセンスしているユーザーにのみ適用されます。 この製品を米国外で入手した場合は、ソフトウェアパッケージに付属の子会社の情報カードを使用するか、Microsoft のアクセシビリティ web <A href="http://go.microsoft.com/fwlink/p/?linkid=18139">http://go.microsoft.com/fwlink/p/?linkId=18139</A>サイトにアクセスして、microsoft サポートサービスの電話番号と住所の一覧を参照してください。 このセクションに記載されている製品とサービスの種類が、お住まいの地域で利用可能かどうかを確認するには、お住まいの地域に連絡してください。 Microsoft 製品に含まれているアクセシビリティ機能の詳細については、「Microsoft 製品の web サイトのアクセシビリティ」を参照してください。



</div>

<div>

## <a name="accessibility-features-of-windows"></a>Windows のユーザー補助機能

Windows オペレーティングシステムには、入力やマウスの使用が困難な方、視覚に障碍のある方、または聴覚障碍のある方にとって役立つ、さまざまなアクセシビリティ機能が用意されています。 これらの機能は、セットアップ時にインストールされます。 これらの機能の詳細については、「Windows の[http://go.microsoft.com/fwlink/p/?linkId=18139](http://go.microsoft.com/fwlink/p/?linkid=18139)ヘルプまたは Microsoft のアクセシビリティ」を参照してください。

  - **無料のステップバイステップガイド**   Microsoft は、コンピューター上のアクセシビリティオプションと設定を調整するための詳しい手順を説明する一連のステップバイステップガイドを提供しています。 この情報は、マウス、キーボード、または両方の組み合わせを使用する方法を学習できるように、左右に並べて表示されます。
    
    Microsoft 製品のステップバイステップガイドについては、「Microsoft の[http://go.microsoft.com/fwlink/p/?linkId=18139](http://go.microsoft.com/fwlink/p/?linkid=18139)アクセシビリティ」を参照してください。

  - **Windows 向けの支援技術製品**   には、障碍のある方に簡単にコンピューターを使用できるように、さまざまな支援技術製品が用意されています。 Microsoft アクセシビリティ web サイトの Windows で実行される支援技術製品のカタログを検索すること[http://go.microsoft.com/fwlink/p/?linkId=18139](http://go.microsoft.com/fwlink/p/?linkid=18139)ができます。
    
    支援技術を利用している場合は、ソフトウェアまたはハードウェアをアップグレードする前に支援技術のベンダーに連絡して、互換性の問題がないか確認してください。

</div>

<div>

## <a name="documentation-in-alternative-formats"></a>別の形式のドキュメント

印刷資料の読み取りや処理が困難な場合は、よりアクセシビリティの高い形式で、多くの Microsoft 製品のドキュメントを入手できます。 Microsoft アクセシビリティ web サイトで、アクセシビリティの高い製品ドキュメントのインデックスを取得[http://go.microsoft.com/fwlink/p/?linkId=18139](http://go.microsoft.com/fwlink/p/?linkid=18139)できます。

さらに、失読症、Inc. (RFB\&D) のブラインド & の記録から、その他の Microsoft のドキュメントを取得することもできます。 RFB\&D は、これらのドキュメントを、配布サービスの登録済みの対象メンバーに配布します。 Microsoft プレスの microsoft 製品ドキュメントと書籍の可用性の詳細については、\&RFB D にお問い合わせください。


<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>ブラインド&amp;失読症, inc. のレコーディング</p>
<p>20 roszel の交通</p>
<p>PrinNJ 08540</p>
<p>米国内からの電話番号: (800) 221-4792</p>
<p>Web サイト: のブラインド&amp;失読症の記録<a href="http://www.rfbd.org/" class="uri">http://www.rfbd.org/</a></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="customer-service-for-people-with-disabilities"></a>障碍のある方のためのカスタマーサービス

Microsoft は、障碍のある方を含め、すべてのユーザーに最適なエクスペリエンスを提供したいと考えています。 ヘルプが必要な場合は、skype のアクセシビリティサポートチームに連絡してください。 skype は、電話やメールで障碍のあるユーザーを支援します。

[障碍の Answer Desk に連絡する](http://support.microsoft.com/gp/contact-microsoft-accessibility)

直通電話: 1-800-936-5900

TTY: 1-800-892-5234

平日: 午前5時 -午後9時 (太平洋標準時)

週末: 午前6時 ~ 午後3時 (太平洋標準時)

</div>

<div>

## <a name="customer-service-for-people-with-hearing-impairments"></a>聞くことに困難のある方のためのカスタマー サービス

聴覚に障碍のある方は、テキスト電話 (TTY/TDD) サービスを利用して、Microsoft 製品とカスタマーサービスに完全にアクセスできます。

  - カスタマサービスについては、Microsoft の売上情報センター (800) 892-5234 (6:30 am) にお問い合わせください。 午後5:30 太平洋標準時 (休日を除く) 月曜日 ~ 金曜日。

  - 米国のテクニカルサポートについては、Microsoft 製品サポートサービス (800) 892-5234 (6:00 am) にお問い合わせください。 午後6:00 太平洋標準時 (休日を除く) 月曜日 ~ 金曜日。 カナダの場合は、8:00 A.M. の間の 568-9641 (905) 午後8:00 東部標準時 (祝祭日を除く) 月曜日から金曜日までの時間。

Microsoft サポートサービスには、サービスを使用する時点での料金、条項、条件が適用されます。 詳細については、の[http://go.microsoft.com/fwlink/p/?linkId=18142](http://go.microsoft.com/fwlink/p/?linkid=18142)Microsoft サポートに関するページを参照してください。

</div>

</div>

<div>

## <a name="for-more-information"></a>関連情報

障碍のある方の生活を向上させるために、コンピューターのアクセシビリティ技術の詳細について[http://go.microsoft.com/fwlink/p/?linkId=18139](http://go.microsoft.com/fwlink/p/?linkid=18139)は、「Microsoft のアクセシビリティ」を参照してください。

</div>

</div>

<span> </span>

</div>

</div>

</div>

