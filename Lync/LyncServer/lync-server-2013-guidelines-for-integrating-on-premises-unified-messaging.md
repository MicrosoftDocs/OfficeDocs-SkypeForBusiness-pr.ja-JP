---
title: 'Lync Server 2013: 内部設置型ユニファイド メッセージングを統合するためのガイドライン'
TOCTitle: 内部設置型ユニファイド メッセージングおよび Lync Server を統合するためのガイドライン
ms:assetid: 829ac017-6907-40f9-be22-787a28eae0ac
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg398656(v=OCS.15)
ms:contentKeyID: 48272728
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 内部設置型ユニファイド メッセージングおよび Lync Server 2013 を統合するためのガイドライン

 

_**トピックの最終更新日:** 2016-12-08_

次に示すのは、エンタープライズ VoIP の展開時に考慮すべきガイドラインおよびベスト プラクティスです。


> [!IMPORTANT]
> Exchange ユニファイド メッセージング (UM) が IPv6 をサポートするのは、UCMA 4 も使用されている場合のみです。



  - Lync Server 2013 Standard Edition サーバーまたは フロント エンド プールを展開します。インストールの詳細については、「展開」のドキュメントの「[Lync Server 2013 の展開](lync-server-2013-deploying-lync-server.md)」を参照してください。

  - スムーズに問題なく統合できるように、Exchange 管理者と協力して、各自が実施する作業を確認します。

  - Exchange UM を有効にする各 Exchange ユニファイド メッセージング (UM) フォレストに、Exchange メールボックス サーバーの役割を展開します。Exchange サーバーの役割のインストールに関する詳細については、Microsoft Exchange Server 2013 のドキュメントを参照してください。
    

    > [!IMPORTANT]
    > Exchange ユニファイド メッセージング (UM) はインストール時に、自己署名証明書を使用するように構成されています。<BR>ただし、自己署名証明書では、Lync Server 2013 と Exchange UM が相互に信頼することはできません。相互に信頼するには、両方のサーバーが信頼する証明機関に個別の証明書を要求する必要があります。



  - Lync Server 2013 と Exchange UM がそれぞれ別のフォレストにインストールされている場合、Lync Server 2013 フォレストを信頼するようにそれぞれの Exchange フォレストを構成し、それぞれの Exchange フォレストを信頼するように Lync Server 2013 フォレストを構成します。また、Lync Server 2013 フォレストのユーザー オブジェクトに関するユーザーの Exchange UM 設定を、通常はスクリプトまたは Identity Lifecycle Manager (ILM) のようなクロス フォレスト ツールを使用して設定します。

  - 必要に応じて、ユニファイド メッセージング サーバーを管理するのに Exchange 管理コンソールをインストールします。

  - Outlook Voice Access および自動応答の有効な電話番号を取得します。

  - Microsoft Exchange Server 2010 Service Pack 1 (SP1) よりも前のバージョンの Exchange UM を使用している場合、Exchange UM SIP URI ダイヤル プランとエンタープライズ VoIP ダイヤル プランの名前を調整します。

## 冗長 Exchange UM サーバーの展開


> [!IMPORTANT]
> 組織で構成する各 Exchange UM SIP URI ダイヤル プランに対して Exchange UM サービスが実行しているサーバーを、2 台以上展開することをお勧めします。拡張された処理能力を提供することに加えて、冗長サーバーを展開することは高可用性を提供します。サーバー障害が発生した場合に、別のサーバーにフェールオーバーするように Lync Server 2013 を構成できます。



次に示すのは、Exchange UM の復元性を提供する構成例です。

**例 1:Exchange UM の復元性**

![Exchange UM の例 1](images/Gg398656.3644b847-0847-4550-a989-e3fc51de5c4b(OCS.15).jpg "Exchange UM の例 1")

例 1 では、Exchange UM サーバー 1 と 2 は Tukwila のデータ センターで有効化されています。Exchange UM サーバー 3 と 4 は Dublin のデータ センターで有効化されています。Tukwila で Exchange UM サーバーが停止した場合、サーバー 1 と 2 のドメイン ネーム システム (DNS) A レコードを、サーバー 3 と 4 それぞれに向くよう、構成します。Dublin で Exchange UM サーバーが停止した場合、サーバー 3 と 4 の DNS A レコードを、サーバー 1 と 2 それぞれに向くよう、構成します。

> [!NOTE]  
> 例 1 の場合はまた、それぞれの Exchange UM サーバーで次の証明書のうちの 1 つを割り当てます。
> <ul><li><p>サブジェクト名の別名 (SAN) に、ワイルドカードの証明書を使用します。</p></li>
> <li><p>SAN に 4 台の Exchange UM サーバーそれぞれの完全修飾ドメイン名 (FQDN) を使用します。</p></li></ul>


**例 2:Exchange UM の復元性**

![Exchange UM の例 2](images/Gg398656.15754273-306e-448d-b258-84bc2936a2e8(OCS.15).jpg "Exchange UM の例 2")

例 2 では、通常の操作条件の下、Exchange UM サーバー 1 と 2 は Tukwila のデータ センターで有効化されています。Exchange UM サーバー 3 と 4 は Dublin のデータ センターで有効化されています。 4 台すべてのサーバーが Tukwila のユーザーの SIP URL ダイヤル プランに含まれていますが、サーバー3 と 4 は有効化されていません。 たとえば、Tukwila で Exchange UM サーバーが停止した場合、Exchange UM サーバー 1 と 2 は無効化され、Tukwila の Exchange UM トラフィックが Dublin のサーバーにルーティングされるよう、Exchange UM サーバー 3 と 4 は有効化されます。

ユニファイド メッセージングを Exchange 2013 で有効または無効にする方法の詳細については、「Microsoft Lync Server 2013 プレビュー」([http://go.microsoft.com/fwlink/?linkid=265372\&clcid=0x411](http://go.microsoft.com/fwlink/?linkid=265372%26clcid=0x411)) を参照してください。

Microsoft Exchange Server 2010 でユニファイド メッセージングを有効にするまたは無効にする方法については、次を参照してください。

  - Exchange 2010 でユニファイド メッセージングを有効にする ([http://go.microsoft.com/fwlink/?linkid=204418\&clcid=0x411](http://go.microsoft.com/fwlink/?linkid=204418%26clcid=0x411))

  - Exchange 2010 でユニファイド メッセージングを無効にする ([http://go.microsoft.com/fwlink/?linkid=204416\&clcid=0x411](http://go.microsoft.com/fwlink/?linkid=204416%26clcid=0x411))

## 関連項目

#### 概念

[内部設置型ユニファイド メッセージングと Lync Server 2013 を統合するための展開プロセス](lync-server-2013-deployment-process-for-integrating-on-premises-unified-messaging.md)

