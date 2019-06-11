---
title: Lync でユーザーの写真を表示する方法
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: How user photos are displayed in Lync
ms:assetid: b44a364d-a1d2-4d45-b27a-b5f77775e233
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn783119(v=OCS.15)
ms:contentKeyID: 62835297
ms.date: 08/27/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 941c1ab56feea557dfc792ea0af6415dd2a56851
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840872"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="how-user-photos-are-displayed-in-lync"></a>Lync でユーザーの写真を表示する方法

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2014-08-25_

**概要:** Lync クライアントに表示されるユーザーの写真は、どの Lync 機能を使用しているかによって異なる場合があります。たとえば、会議中や IM チャット中などです。

Lync 2010 では、他の Lync ユーザーに対して表示される、Lync プロファイルと共に写真を含める機能が導入されました。 Lync クライアントで連絡先の写真を表示するかどうかを選択することもできます。 Lync 2013 では、高解像度の写真をユーザー向けにサポートします。 このトピックでは、Lync クライアントでユーザーの写真を取得して表示する方法、画像が保存されている場所、各画像ソースの制限事項、さまざまな Lync サービスでユーザーの写真を使用する方法について説明します。

<div>

## <a name="planning-considerations"></a>計画の考慮事項

ユーザー写真のサポートを実装する計画を立てる場合は、次の点を考慮する必要があります。

  - 高解像度ユーザーの写真のサポートでは、ユーザーのメールボックスを Exchange 2013 に配置し、Lync ユーザーアカウントを Lync 2013 プールに置く必要があります。

  - 高精細ユーザーの写真は、Lync Server 2013 と Exchange 2013 の両方が使用されている環境でのみサポートされます。

  - Exchange 2010 上のメールボックスを使用しているユーザーは、常に、ユーザー写真のソースとして AD DS の**thumbnailPhoto**属性を使用します。

  - AD DS から**thumbnailPhoto**属性として保存されているユーザー写真は、外部/フェデレーションの連絡先には表示されません。

  - ユーザーの連絡先の写真が AD DS に保存されている場合、使用される画像ファイルは96×96ピクセルで、100 KB のファイルサイズに制限されています。

  - Lync Server と Exchange Server の間の接続が失われた場合、AD DS からのユーザーの低解像度**thumbnailPhoto**が表示され、内部ユーザーのみになります。

  - アクティブなスピーカーでビデオが有効になっていない場合、高解像度のユーザー写真が Lync 2013 会議に表示されます。 また、ギャラリーのサムネイル写真の上にマウスを移動すると、高解像度の写真が表示されます。

</div>

<div>

## <a name="user-photos-in-lync-2010"></a>Lync 2010 でのユーザーの写真

Lync 2010 クライアントでは、次の2つのオプションのいずれかを選択して、自分のプロファイルの写真を表示したり、**既定の会社の画像**を表示したり、 **web アドレスの画像を表示**したりすることができます。

<div>

## <a name="default-corporate-picture"></a>既定の企業の画像

**既定の企業図**オプションを選択すると、Lync は Active Directory ドメインサービスから表示した写真を取得します。 使用される画像は、Active Directory ドメインサービスの**thumbnailPhoto**属性の値として定義されている画像です。 これは、Outlook で画像を表示するために Exchange で使用されるファイルと同じです。

Active Directory ドメインサービスからの画像の使用に関する考慮事項には、次のようなものがあります。

  - 96ピクセルで最大96ピクセルのサイズの画像のみがサポートされます。 画像のファイルサイズは、100 KB に制限されています。

  - 既定では、ユーザーは**thumbnailPhoto**属性に使用される画像を変更できますが、Lync クライアントから直接変更することはできません。 Active Directory ドメインサービスを使用して、これを無効にすることができます。

  - Active Directory ドメインサービスに保存されている画像は、フェデレーションされた連絡先である場合でも、組織外の連絡先には表示されません。

  - 大規模な組織では、多数のユーザーのために画像を保存して取得すると、Active Directory ドメインサービスのデータベースのサイズとパフォーマンスに影響する可能性があります。

  - 限られた画像サイズとファイルサイズは、低解像度の画像のみを使用できることを意味します。

<div>

## <a name="how-users-manage-their-user-photos-in-active-directory-domain-services"></a>Active Directory ドメインサービスでユーザーの写真を管理する方法

ユーザーは、Lync 2010 クライアントを介して、Active Directory ドメインサービスプロファイルで使用されている画像を変更することはできません。 使用できる場合は、次のいずれかのオプションを使うことができます。

  - **Sharepoint server**   ユーザーは、sharepoint サーバー上の [個人用サイト] に写真をアップロードし、 [sharepoint でプロファイルの同期を構成](http://go.microsoft.com/fwlink/p/?linkid=507466)して、その写真を Active Directory ドメインの**thumbnailPhoto**属性と同期させることができます。サービス.

  - **公開されているアクセシビリティ**   の高い url に保存されている写真ユーザーは、使用する画像の公開可能な url を指定してユーザーの写真を構成できます。 画像には、パスワードなしでアクセスできるようにする必要があります。 指定した web アドレスに保存されている画像は、プレゼンス情報の連絡先カードカテゴリを通じて他のユーザーに転送されます。 Lync クライアントでユーザーの写真を表示する必要がある場合は、指定した web アドレスから画像を取得します。

  - **Windows PowerShell**   管理者の exchange 2010 コマンドレットでは、thumbnailPhoto 属性を管理するために、exchange 2010 の管理シェルで、 **** の[インポートのプロパティ](http://go.microsoft.com/fwlink/p/?linkid=507468)レットを実行できます。 Exchange 2010 コマンドレットを使用して画像をインポートすると、ファイルサイズは 10 KB に制限されます。

  - **サードパーティのツール**   ユーザーは、自分の写真だけを**thumbnailPhoto**属性にアップロードできます。

</div>

</div>

<div>

## <a name="show-a-picture-from-a-web-address"></a>Web アドレスの画像を表示する

[ **Web アドレスから画像を表示**する] オプションを選ぶと、lync では、入力したアドレスに画像が表示され、lync でユーザー写真の画像が表示されます。

Web アドレスからの画像の使用に関する考慮事項には、次のものがあります。

  - ファイルサイズの制限は、[新しい-CsClientPolicy](http://go.microsoft.com/fwlink/p/?linkid=507463)コマンドレットで定義された、クライアントポリシーの**Maxphotosizekb**属性によって決定されます。 既定のサイズ制限は、30 KB です。 最大値は 100 KB です。 画像の解像度には制限はありませんが、サイズ制限を超えている画像ファイルを使用しようとしても、Lync クライアントにダウンロードされません。 この値を0に設定すると、すべてのユーザーの写真を Lync で使用できなくなります。

  - Web アドレスからのユーザーの写真は、フェデレーションされた外部の連絡先から見ることができます。

</div>

<div>

## <a name="managing-users-photo-with-client-policy-cmdlets"></a>クライアントポリシーコマンドレットを使用してユーザーの写真を管理する

Lync Server 2010 では、クライアントポリシー設定は CsClientPolicy コマンドレットで構成されています。 構成済みのポリシー設定は、インバンドプロビジョニングを通じてクライアントに送信されます。 ユーザーの写真エクスペリエンスを決定する CsClientPolicy コマンドレットの2つのパラメーターは、 **DisplayPhoto**と**Maxphotosizekb**です。 **DisplayPhoto**と**Maxphotosizekb**の対応するインバンドプロビジョニングパラメーターは、 **PhotoUsage**という名前です。 **PhotoUsage**パラメーターの値は、 **endpointConfiguration** **provisionGroup**経由でクライアントに送信されます。 詳細については[、「クライアントポリシーと設定の概要](http://go.microsoft.com/fwlink/?linkid=507470)」を参照してください。

**DisplayPhoto**パラメーターの値は、ユーザーの写真イメージのソースを決定します。 サポートされている値は、次の表に記載されています。


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>DisplayPhoto パラメーター値</th>
<th>画像ソース</th>
<th>Lync 2010 クライアントの設定</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>NoPhoto</p></td>
<td><p>なし</p></td>
<td><p><strong>自分の写真を表示しない</strong></p></td>
</tr>
<tr class="even">
<td><p>PhotoFromADOnly</p></td>
<td><p>Active Directory</p></td>
<td><p><strong>既定の企業の画像</strong></p></td>
</tr>
<tr class="odd">
<td><p>すべての写真</p></td>
<td><p>Web アドレス</p></td>
<td><p><strong>Web アドレスの画像を表示する</strong></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="how-lync-2010-client-gets-photos"></a>Lync 2010 クライアントで写真を取得する方法

Lync 2010 では、ユーザーの写真はアドレス帳サービスによってサーバー上で管理されます。 Lync クライアントは、最初に、配布リスト展開 web サービスを通じて公開されるサーバー上のアドレス帳 Web クエリ (ABWQ) サービスを照会することによって、ユーザーの写真を取得します。 クライアントはイメージファイルを受け取り、ユーザーのキャッシュにコピーして、表示する必要があるたびにイメージをダウンロードしないようにします。 クエリから返された属性値は、ユーザーのキャッシュされたアドレス帳サービスエントリにも格納されます。 アドレス帳サービスは、キャッシュされているすべての画像を24時間ごとに削除します。つまり、サーバー上のキャッシュで新しいユーザーの画像が更新されるまでに最大24時間かかる可能性があります。 [CsAddressBook](https://docs.microsoft.com/powershell/module/skype/Update-CsAddressBook)コマンドレットを使用して、キャッシュを強制的に更新できます。

プレゼンス状態に含まれているユーザーの写真にも、新しい画像が利用可能かどうかを判断するために Lync クライアントによって使用されるハッシュ値が関連付けられています。 プレゼンス状態で使用される画像ファイルへの変更がクライアントに自動的に通知されます。

<div class=" ">


> [!NOTE]  
> 写真は GalContacts データベースに保存されていないため、ユーザーの写真をダウンロードしても、クライアントポリシー (<A href="http://go.microsoft.com/fwlink/p/?linkid=507508">CsClientPolicy</A>) の<STRONG>addressbookavailability</STRONG>の設定に依存していません。



</div>

ABWQ サービスへのクエリには、次の属性が含まれています。

  - **Photohash**の写真が変更されたかどうかを判断するために使用される、バイナリ写真データのハッシュ値。   

  - ****   サーバーに保存されている画像ファイルへの相対パスを PhotoRelPath します。

  - **[Photosize**   ] 画像ファイルのサイズ (バイト単位) です。

  - **タイムスタンプ**   イメージファイルが最後にサーバーからダウンロードされ、クライアントキャッシュにコピーされた日時です。

次に、画像ファイルを取得した後、Lync 2010 クライアントは、クエリから返された属性値と、インバンドプロビジョニングからクライアントが受け取った属性値とを比較して、それらが異なるかどうかを確認します。 値が異なる場合、クライアントは、サインインしたユーザーの画像ファイルを HTTP GET 要求で取得します。

さらに、クライアントは、キャッシュされたバージョンのイメージファイルが作成された時点から24時間ごとにサーバーに確認して、サーバー上の**Photohash**属性の値とクライアント上の値とを比較します。 値が異なる場合は、画像ファイルが変更されていることがクライアントに認識されます。 更新された画像ファイルを取得するために、クライアントはもう一度 ABWQ サービスを照会して、クライアントキャッシュのイメージファイルをサーバー上の画像ファイルに更新します。これにより、クライアントキャッシュ内のファイルの**タイムスタンプ**もリセットされます。

次に示すのは、ABWQ サービスへのクエリに対する応答の例です。

    <Attribute>
              <Name>PhotoRelPath</Name>
              <Value>efa6096aed2746cb9ab2037f7dbdde9d.f2eeeb5946db54a7aa607ecd3ae09d
              95.photo</Value>
              <Values xmlns:d6p1="http://schemas.microsoft.com/2003/10/Serialization/Arrays" i:nil="true" />
    </Attribute>
    <Attribute>
              <Name>PhotoHash</Name>
              <Value>f2eeeb5946db54a7aa607ecd3ae09d95</Value>
              <Values xmlns:d6p1="http://schemas.microsoft.com/2003/10/Serialization/Arrays" i:nil="true" />
    </Attribute>
    <Attribute>
         <Name>PhotoSize</Name>
         <Value>4620</Value>
         <Valuesxmlns:d6p1="http://schemas.microsoft.com/2003/10/Serialization/Arrays"
    i:nil="true" />
    </Attribute>

</div>

</div>

<div>

## <a name="user-photos-in-lync-2013"></a>Lync 2013 でのユーザーの写真

Lync 2013 では、ユーザー写真用の高解像度の画像のサポートが導入されました。 Lync 2013 には、ユーザーの写真を Exchange 2013 上のユーザーのメールボックスに保存する機能もサポートされています。これにより、Lync 2010 に含まれる画像の解像度とサイズの制限が削除されます。 Lync 2013 でのユーザーの写真は、最大 20 MB のファイルサイズで、648ピクセルで最大648ピクセルにすることができます。 Lync 2013 の高解像度の写真は、Exchange 2013 のユーザーのメールボックスに配置されている必要があります。また、Lync 2013 クライアントでのみサポートされます。 Exchange との統合により、2013バージョンの Lync、Exchange、および SharePoint の Oauth という新しい承認フレームワークが利用されます。

展開で Exchange 2013 が使用されていない場合、ユーザーの写真のサポートは Lync 2010 と同じです。 ただし、使用する写真を選ぶためのユーザーオプションは、Lync 2013 クライアントでは異なります。 Lync 2013 クライアントでは、ユーザーは [**写真を非表示**にする] または [**マイピクチャを表示**する] のいずれかを選ぶことができます。 [ **Web サイトの画像を表示**する] オプションは既定では利用できませんが、クライアントポリシーを割り当てることで有効にすることができます。

<div>

## <a name="hide-my-picture"></a>写真を表示しない

ユーザー写真の設定は、Lync 2013 の [**オプション**] ダイアログにあります。 [自分の**写真を表示**しない] を選ぶと、lync クライアントではユーザーの写真は表示されませんが、自分の写真は連絡先カードと lync の外部に表示されたままになります。

</div>

<div>

## <a name="show-my-picture"></a>自分の写真を表示

**[自分の写真を表示**する] オプションを選択すると、lync クライアントおよび lync での会話で他のユーザーにユーザーの写真が表示されます。 使用されている画像は、AD DS に保存されているものです。

</div>

<div>

## <a name="show-a-picture-from-a-website"></a>Web サイトの画像を表示する

クライアントポリシーを有効にするように設定した後、[ **web サイトの画像を表示**する] オプションが Lync 2013 で使用できるようになります。 クライアントバージョンは、Lync 累積更新プログラムと共にインストールされている15.0.4535.1002 よりも新しいバージョンである必要があります。 [2013 年11月](http://go.microsoft.com/fwlink/p/?linkid=509908)。 クライアントの変更を確認するには、ユーザーがもう一度ログアウトしてから再びログインしなければならない場合があります。

Lync Server 管理シェルで[set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy)ポリシーを実行して、 **web サイトの設定から画像が表示**されるようにクライアントポリシーを設定することができます。 展開内のすべてのユーザーに対してグローバルにポリシーを設定する方法を示すコマンドレットの例を次に示します。

   ```
    $pe=New-CsClientPolicyEntry -Name EnablePresencePhotoOptions -Value True
   ```

   ```
    $po=Get-CsClientPolicy -Identity Global
   ```

   ```
    $po.PolicyEntry.Add($pe)
   ```

   ```
    Set-CsClientPolicy -Instance $po
   ```


ユーザーのメールボックスに画像がアップロードされると、Exchange では、クライアントアプリケーションで使用できる画像の低解像度バージョンが自動的に作成されます。 また、ユーザーの写真は、AD DS でも更新されます。

<div class=" ">


> [!NOTE]  
> AD DS でイメージファイルが更新されると、48 x 48 ピクセルのイメージが作成され、AD DS の thumbnailPhoto に使用されます。 既存の画像はすべて置き換えられます。 そのため、96 x 96 のイメージを AD DS に追加した場合は、新しい 48 x 48 イメージによって上書きされます。 これは重要なのは、Lync 2010 クライアントを使用している環境内にユーザーがいて、ユーザーの写真が AD DS から取得されるためです。 組織内に Lync 2010 クライアントがある場合は、96 x 96 ピクセルのイメージをインポートして、AD DS によって作成されたものを置き換えることができます。



</div>

</div>

<div>

## <a name="user-photo-support-in-lync-2013"></a>Lync 2013 でのユーザー写真のサポート

Lync 2013 では、次の表に示すように、ユーザーの写真で3つの画像解像度がサポートされています。 使用される画像は、Lync ユーザーに割り当てられているクライアントポリシーの設定によって決まります。 詳細については、このトピックの「クライアントポリシーコマンドレットを使用してユーザーの写真を管理する」を参照してください。


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>画像の解像度 (ピクセル)</th>
<th>アプリケーション</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>48 x 48</p></td>
<td><p>高解像度の画像が選択されていない場合に使用されます。</p></td>
</tr>
<tr class="even">
<td><p>96 x 96</p></td>
<td><p>Outlook Web App および Outlook 2013 で使用</p></td>
</tr>
<tr class="odd">
<td><p>648 x 648</p></td>
<td><p>Lync 2013 デスクトップクライアントおよび Lync 2013 Web アプリで使用</p></td>
</tr>
</tbody>
</table>


Exchange 2013 でメールボックスが有効になっているユーザーは、高解像度の写真など、Outlook Web Access または Lync 2013 クライアントオプションを使用して、別の画像をアップロードできます。 使用する画像の推奨設定は次のとおりです。

  - ****   648 x 648 ピクセルの画像解像度

  - **色深度**   24 ビット

  - **画像ファイルのサイズ**   が最大 20 MB

  - **ファイル形式**   JPEG

648ピクセル x 648 ピクセルの標準的な24ビット JPEG 画像のファイルサイズは約 240 KB であるため、4ユーザー写真ごとに 1 MB の記憶領域が必要です。

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

