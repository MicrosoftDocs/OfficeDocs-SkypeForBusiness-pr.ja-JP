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
ms.openlocfilehash: d3e374825b762d059cc4b56a232d8e8b518319bf
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48523234"
---
# <a name="accessibility-in-lync-server-2013"></a>Lync Server 2013 でのアクセシビリティ

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2014-10-09_

Microsoft では、すべてのユーザーにとって使いやすい製品とサービスを提供できるよう取り組んでいます。 次のセクションでは、障碍がある方のために Lync Server 2013 をより使いやすくするために役立つ機能、製品、およびサービスについて説明します。

<div>

## <a name="accessibility-features-of-lync-server-2013"></a>Lync Server 2013 のユーザー補助機能

Lync Server 2013 の次の機能を使用すると、障碍のある方がアクセスしやすくなります。

  - キーボード ショートカット

  - 図の代替テキスト

また、Windows のユーザー補助機能とツールの中には、Lync Server ユーザーに障害が発生する利点があります。 Windows PowerShell のサイズと色の変更によって、Lync Server 管理シェルを使用する場合のユーザー補助オプションが提供されます。 Windows PowerShell のユーザー補助オプションの詳細については、TechNet ライブラリの「Windows PowerShell 2.0 でのアクセシビリティ」を参照してください [https://go.microsoft.com/fwlink/p/?linkId=98964](https://go.microsoft.com/fwlink/p/?linkid=98964) 。

</div>

<span id="BKMK_KeyboardShortcuts"></span>

<div>

## <a name="keyboard-shortcuts"></a>キーボード ショートカット

Lync Server 管理ツールおよびその他の機能のユーザーインターフェイスを操作するには、キーボードショートカットを使用できます。

キーボード ショートカットを使用することによって、次のような一般的なタスクを迅速に実行できます。


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>操作内容</th>
<th>使用するキーボード ショートカット</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>ユーザー インターフェイスの要素の間で切り替える</p></td>
<td><p>Tab</p></td>
</tr>
<tr class="even">
<td><p>[<strong>すべて表示</strong>]、[<strong>すべて非表示</strong>]、ハイパーリンクのオープンなど、選択した要素に対してアクションを実行する</p></td>
<td><p>次のように入力します</p></td>
</tr>
<tr class="odd">
<td><p>選択要素をページまたはメニューの次の要素に変更する</p></td>
<td><p>Tab</p></td>
</tr>
<tr class="even">
<td><p>選択要素をページの前の要素に変更する</p></td>
<td><p>Shift + Tab</p></td>
</tr>
<tr class="odd">
<td><p>ページまたはメニューで選択要素を上、下、左、右に変更する</p></td>
<td><p>方向キー</p></td>
</tr>
<tr class="even">
<td><p>ツリーの選択されたノードを展開する</p></td>
<td><p>+ 要点</p></td>
</tr>
<tr class="odd">
<td><p>ツリーの選択されたノードを折りたたむ</p></td>
<td><p>- 要点</p></td>
</tr>
<tr class="even">
<td><p>メニュー バーにアクセスする</p></td>
<td><p>Alt キー</p></td>
</tr>
<tr class="odd">
<td><p>メニュー バー コマンドにアクセスする</p></td>
<td><p>Alt + ショートカット メニューで下線の付いている文字</p></td>
</tr>
<tr class="even">
<td><p>証明書ウィザードでドロップダウン リストを選択する</p></td>
<td><p>Tab</p></td>
</tr>
<tr class="odd">
<td><p>証明書ウィザードでドロップダウン リストを開く</p></td>
<td><p>Ctrl + Space</p></td>
</tr>
<tr class="even">
<td><p>証明書ウィザードでドロップダウン リストの項目を強調表示する</p></td>
<td><p>Tab キーを押した後、Ctrl キーを押しながら方向キーを押して項目間を移動</p></td>
</tr>
<tr class="odd">
<td><p>証明書ウィザードでドロップダウン リストの項目を選択または選択解除する</p></td>
<td><p>Ctrl + Space</p></td>
</tr>
</tbody>
</table>


</div>

<span id="BKMK_AltText"></span>

<div>

## <a name="alternate-text-for-figures"></a>図の代替テキスト

Lync Server 2013 のヘルプのすべての図には、スクリーンショット、図、フローチャート、その他の図を含む代替テキストが関連付けられています。 図を見ることが困難なユーザーは、図の上にカーソルを置くと、代替テキストを読むことができます。 代替テキストには、図の内容が説明されています。

</div>

<span id="BKMK_AccessMS"></span>

<div>

## <a name="accessibility-products-and-services-from-microsoft"></a>マイクロソフトが提供するユーザー補助製品およびサービス

次のセクションでは、障碍がある方のために Windows をより使いやすくするための機能、製品、およびサービスについて説明します。

<div>


> [!NOTE]  
> ここに記載されている情報は、米国内で Microsoft 製品のライセンスを取得しているユーザーのみが対象となります。 この製品を米国外で購入した場合は、ソフトウェアパッケージに付属の子会社情報カードを使用するか、microsoft アクセシビリティ web サイトにアクセスして、 <A href="https://go.microsoft.com/fwlink/p/?linkid=18139">https://go.microsoft.com/fwlink/p/?linkId=18139</A> microsoft サポートサービスの電話番号と住所の一覧を参照できます。 ここで説明する種類の製品やサービスがお住まいの地域で利用できるかどうかについては、お近くの子会社に問い合わせてください。 マイクロソフト製品に含まれているユーザー補助機能の詳細については、Web サイト「Accessibility in Microsoft Products」を参照してください。



</div>

<div>

## <a name="accessibility-features-of-windows"></a>Windows のユーザー補助機能

Windows オペレーティング システムには、キーボード入力やマウスの使用が困難な方や、視覚や聴覚に障碍がある方に役立つ、ユーザー補助機能が多数組み込まれています。 これらの機能は、セットアップ中にインストールされます。 これらの機能の詳細については、「Windows ヘルプまたは Microsoft アクセシビリティ」を参照してください [https://go.microsoft.com/fwlink/p/?linkId=18139](https://go.microsoft.com/fwlink/p/?linkid=18139) 。

  - **無料のステップバイステップのチュートリアル**    Microsoft では、コンピューター上のユーザー補助のオプションと設定を調整するための詳細な手順を説明する一連のステップごとのチュートリアルが用意されています。 この情報は隣り合わせに表示されるため、マウス、キーボード、またはその組み合わせの使用方法がひとめでわかります。
    
    Microsoft 製品のステップバイステップのチュートリアルについては、「Microsoft Accessibility」を参照してください [https://go.microsoft.com/fwlink/p/?linkId=18139](https://go.microsoft.com/fwlink/p/?linkid=18139) 。

  - Windows 用の**支援技術製品**    障碍のある方がコンピューターを使いやすくするために、さまざまな支援技術製品を利用できます。 Microsoft アクセシビリティ web サイト上の Windows 上で実行されている支援技術製品のカタログは、で検索でき [https://go.microsoft.com/fwlink/p/?linkId=18139](https://go.microsoft.com/fwlink/p/?linkid=18139) ます。
    
    補助テクノロジを使用する場合は、ソフトウェアまたはハードウェアをアップグレードする前に、互換性の問題がないかどうかを補助テクノロジ ベンダーにお問い合わせください。

</div>

<div>

## <a name="documentation-in-alternative-formats"></a>代替形式のドキュメント

Microsoft 製品のドキュメントの多くは、印刷されたドキュメントが読みにくい、または扱いにくい方でも快適にご利用いただけるよう、さまざまな形態で入手できます。 アクセス可能な製品ドキュメントのインデックスは、Microsoft アクセシビリティ web サイトのから入手でき [https://go.microsoft.com/fwlink/p/?linkId=18139](https://go.microsoft.com/fwlink/p/?linkid=18139) ます。

さらに、ブラインド & Dyslexic (http://www.rfbd.org/http://www.rfbd.org/, Inc (RFB D) の記録から、その他の Microsoft の文書を入手することもでき \& ます。 RFB \& D は、これらのドキュメントを、配布サービスの登録済みの対象となるメンバーに配布します。 Microsoft プレスからの Microsoft 製品ドキュメントおよび書籍の入手については、RFB D を参照してください \& 。


<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>ブラインド &amp; dyslexic (http://www.rfbd.org/http://www.rfbd.org/, Inc のレコーディング</p>
<p>20 Roszel Road</p>
<p>Princeton, NJ 08540</p>
<p>米国内からの電話番号: (800) 221-4792</p>
<p>Web サイト: 次の場所にあるブラインド Dyslexic (http://www.rfbd.org/http://www.rfbd.org/の記録 &amp;<a href="http://www.rfbd.org/" class="uri">http://www.rfbd.org/</a></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="customer-service-for-people-with-disabilities"></a>障碍のある方のためのカスタマーサービス

Microsoft は、障碍のある方を含むすべてのお客様に最適な経験を提供したいと考えています。 サポートが必要な場合は、ユーザー補助サポートチームに連絡してください。電話または電子メールで障碍のある方のためのトレーニングを受けることができます。

[障碍応答デスクに連絡する](https://support.microsoft.com/gp/contact-microsoft-accessibility)

直通電話回線: 1-800-936-5900

TTY: 1-800-892-5234

平日: 午前5時 -9 P.M. (太平洋標準時)

週末: 午前6時 ~ 午後3時 (太平洋標準時)

</div>

<div>

## <a name="customer-service-for-people-with-hearing-impairments"></a>聴覚に障碍がある方のための顧客サービス

聴覚に障碍がある方は、テキスト電話 (TTY/TDD) サービスをご利用いただくと、Microsoft 製品および顧客サービスにアクセスできます。

  - 顧客サービスについては、祝日を除く月曜から金曜の午前 6 時 30 分から午後 5 時 30 分 (太平洋標準時) の間に Microsoft Sales Information Center (電話: (800) 892-5234) までお問い合わせください。

  - 米国内における技術サポートについては、祝日を除く月曜から金曜の午前 6 時から午後 6 時 (太平洋標準時) の間に Microsoft Product Support Services (電話: (800) 892-5234) までお問い合わせください。カナダの場合は、祝日を除く月曜から金曜の午前 8 時から午後 8 時の間に (905) 568-9641 までお問い合わせください。

Microsoft のサポート サービスには、サービス利用時の料金、条項、および条件が適用されます。 詳細については、「Microsoft サポート」を参照してください [https://go.microsoft.com/fwlink/p/?linkId=18142](https://go.microsoft.com/fwlink/p/?linkid=18142) 。

</div>

</div>

<div>

## <a name="for-more-information"></a>詳細情報

障碍のある方がコンピューターの機能を向上させる方法については、「Microsoft Accessibility」を参照してください [https://go.microsoft.com/fwlink/p/?linkId=18139](https://go.microsoft.com/fwlink/p/?linkid=18139) 。

</div>

</div>

<span> </span>

</div>

</div>

</div>

