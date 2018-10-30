---
title: Lync 2013 の新しい設定と変更された設定
TOCTitle: Lync 2013 の新しい設定と変更された設定
ms:assetid: bb13789c-7eda-461c-a387-02ea8ca4dabe
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ205204(v=OCS.15)
ms:contentKeyID: 48273420
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync 2013 の新しい設定と変更された設定

 

_**トピックの最終更新日:** 2015-03-09_

このトピックでは、クライアント管理に直接関連する Lync Server 管理シェル コマンドレットへの変更について説明します。Lync Server 2013 は、いくつかの新しいパラメーターを紹介し、他の方法で構成できる機能の非推奨パラメーターについて説明します。

## 新しいクライアント管理パラメーター


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>新規</th>
<th>Lync Server 管理シェル コマンドレット</th>
<th>説明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>TracingLevel</p></td>
<td><p>CsClientPolicy</p></td>
<td><p>True に設定されている場合、ソフトウェア トレースが Lync で有効になります。False に設定されている場合、ソフトウェア トレースは無効になります。ソフトウェア トレースでは、API 呼び出しの追跡などのプログラムの動作すべてについて、詳細な記録を保持します。トレースは、開発者やアプリケーション サポートの要員にとって特に役立ちます。この設定は、Communications Server 2007 R2 のグループ ポリシー設定 &quot;Communicator のトレースをオンにする&quot; と同等です。設定は次のとおりです。</p>
<ul>
<li><p>Off = トレースは無効です。ユーザーはこの設定を変更できません。</p></li>
<li><p>Light = 最小のトレースが実行されます。ユーザーはこの設定を変更できません。</p></li>
<li><p>On = 詳細なトレースが実行されます。ユーザーはこの設定を変更できません。</p></li>
</ul>
<p>既定では、TracingLevel は null 値に設定されます。この場合、最小限のトレースが実行されますが、ユーザーはこの最小限のトレースを有効または無効にすることができます。 </p></td>
</tr>
<tr class="even">
<td><p>EnableMediaRedirection</p></td>
<td><p>CsClientPolicy</p></td>
<td><p>True ($True) に設定されている場合、オーディオおよびビデオ ストリームを他のネットワーク トラフィックから切り離すことができます。これにより、クライアント デバイスでオーディオおよびビデオのエンコードとデコードをローカルに実行できるようになります。通常、メディア リダイレクトを使用すると、デバイス リモーティングやコーデック圧縮などの類似の手法を使用した場合に比べて帯域幅の使用量が減少し、サーバーのスケーラビリティが向上し、ユーザー エクスペリエンスが最適化されます。</p></td>
</tr>
<tr class="odd">
<td><p>AllowLargeMeetings</p></td>
<td><p>CsConferencing</p></td>
<td><p>このパラメーターを True に設定すると、Lync 会議がすべて &quot;大規模会議&quot; として扱われます。大規模会議では、既定により送信される会議名簿の大きさに加え、参加者に送信される通知の数にも制限が設定されます。</p></td>
</tr>
<tr class="even">
<td><p>DisablePowerPointAnnotations</p></td>
<td><p>CsConferencing</p></td>
<td><p>このパラメーターを True ($True) に設定すると、ユーザーは、会議で使用している PowerPoint スライドに注釈を追加できません。ただし (AllowAnnotations プロパティの値によっては)、ユーザーは他の白板機能にアクセスすることができます。既定値は False で、PowerPoint の注釈が許可されます。</p></td>
</tr>
<tr class="odd">
<td><p>AllowSharedNotes</p></td>
<td><p>CsConferencing</p></td>
<td><p>このパラメーターを True (既定値) に設定すると、会議にリンクされている OneNote ノートブックで開いているものはすべて、会議参加者、会議中に共有された内容詳細などの情報により、自動的に更新されます。</p></td>
</tr>
<tr class="even">
<td><p>EnableInviteCustomization</p></td>
<td><p>CsMeetingConfiguration</p></td>
<td><p>他の新しい CsMeetingConfiguration パラメーターと併用して、Lync 2013 用オンライン ミーティング アドイン により生成される会議出席依頼をカスタマイズします。</p></td>
</tr>
<tr class="odd">
<td><p>LogoURL</p></td>
<td><p>CsMeetingConfiguration</p></td>
<td><p>Lync 2013 用オンライン ミーティング アドイン により生成されるすべての会議出席依頼に組織のロゴを追加します。GIF または JPG 画像の URL を指定します。</p></td>
</tr>
<tr class="even">
<td><p>HelpURL</p></td>
<td><p>CsMeetingConfiguration</p></td>
<td><p>Lync 2013 用オンライン ミーティング アドイン により生成されるすべての会議出席依頼に、組織のヘルプまたはサポートを追加します。</p></td>
</tr>
<tr class="odd">
<td><p>LegalURL</p></td>
<td><p>CsMeetingConfiguration</p></td>
<td><p>Lync 2013 用オンライン ミーティング アドイン により生成されるすべての会議出席依頼に、法的テキストまたは免責テキストを追加します。テキストの場所を示す URL を指定します。</p></td>
</tr>
<tr class="even">
<td><p>CustomFooterText</p></td>
<td><p>CsMeetingConfiguration</p></td>
<td><p>Lync 2013 用オンライン ミーティング アドイン により生成されるすべての会議出席依頼にカスタム フッターを追加します。カスタム フッター テキストの場所を示す URL を指定します。</p></td>
</tr>
<tr class="odd">
<td><p>IsPublicDisclosureAllowed</p></td>
<td><p>CsWebServiceConfiguration</p></td>
<td><p>Lync Web App の新しい 2013 バージョンを有効にします。既定では、Lync Web App の新しいバージョンは無効で、管理者が有効にする必要があります。</p></td>
</tr>
</tbody>
</table>


## 非推奨のクライアント管理パラメーター


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>パラメーター</th>
<th>Lync Server 管理シェル コマンドレット</th>
<th>説明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>EnableSQMData</p></td>
<td><p>CsClientPolicy</p></td>
<td><p>Set-CSClientPolicy コマンドレットの EnableSQMData パラメーターは、Lync Server 2013 から削除されました。代わりにソフトウェア品質管理 (SQM) データ用の共有グループ ポリシーを使用して、Lync クライアントの [一般] オプション ページでカスタマー エクスペリエンス向上プログラム オプション用のユーザー インターフェイスを決定できます。</p>
<p>HKEY_CURRENT_USER\Software\Policies\Microsoft\Office\Common\QMEnable</p>
<p>値:</p>
<p>1 = チェック ボックスを表示および選択します (ユーザーはチェック ボックスをオフにできます)</p>
<p>0 = チェック ボックスをオフにして無効にします (ユーザーは上書きできません)</p>
<p>Null = 値は Office セットアップによって決まります。ユーザーが選択に応じて設定するためのチェック ボックスが表示されます</p></td>
</tr>
<tr class="even">
<td><p>AllowExchangeContactStore</p></td>
<td><p>CsClientPolicy</p></td>
<td><p>このパラメーターは削除されました。その代わり、Lync Server 2013 を展開してトポロジを公開するときは、統合連絡先ストアが既定ですべてのユーザーに対して有効になります。これは、ユーザーのすべての連絡先が Exchange に保持され、Lync、Outlook、および Outlook Web Access で使用できることを意味します。Set-CsUserServicesPolicy コマンドレットを使用して、統合連絡先ストアを使用可能にするユーザーをカスタマイズできます。ユーザーは、グローバル、サイト別、テナント別、個人別、または個人グループ別に有効にできます。詳細については、「<a href="lync-server-2013-enable-users-for-unified-contact-store.md">Lync Server 2013 の統合連絡先ストアでユーザーを有効にする</a>」を参照してください。</p></td>
</tr>
<tr class="odd">
<td><p>MAPIPollInterval</p></td>
<td><p>CsClientPolicy</p></td>
<td><p>このパラメーターは Lync 2013 では使用されません。このパラメーターは以前のリリースで、クライアントが Exchange のパブリック フォルダーから MAPI データを取得する頻度を指定していました。</p></td>
</tr>
</tbody>
</table>

