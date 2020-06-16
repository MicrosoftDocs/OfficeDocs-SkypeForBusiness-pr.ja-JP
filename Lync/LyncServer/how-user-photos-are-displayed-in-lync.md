---
title: Lync でユーザーの写真を表示する方法
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: How user photos are displayed in Lync
ms:assetid: b44a364d-a1d2-4d45-b27a-b5f77775e233
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn783119(v=OCS.15)
ms:contentKeyID: 62835297
ms.date: 08/27/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 88d6f6f6f5578994831fd15329988d963a295832
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755441"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="how-user-photos-are-displayed-in-lync"></a>Lync でユーザーの写真を表示する方法

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2014-08-25_

**概要:** Lync クライアントに表示されるユーザーの写真は、会議や IM チャットなど、どの Lync 機能を使用しているかによって異なる場合があります。

Lync 2010 には、他の Lync ユーザーに表示される Lync プロファイルに写真を含める機能が導入されています。 また、Lync クライアントで連絡先の写真を表示するかどうかを選択することもできます。 Lync 2013 では、ユーザーの高解像度写真のサポートがサポートされています。 このトピックでは、Lync クライアントがユーザーの写真を取得および表示する方法、画像が格納される場所、各画像ソースの制限、およびさまざまな Lync サービスでユーザーの写真を使用する方法について説明します。

<div>

## <a name="planning-considerations"></a>計画に関する考慮事項

ユーザー写真のサポートの実装を計画するときは、次の点を考慮する必要があります。

  - 高精細ユーザーの写真サポートを使用するには、ユーザーのメールボックスが Exchange 2013 上にあり、lync ユーザーアカウントが Lync 2013 プールに配置されている必要があります。

  - 高精細ユーザーの写真は、Lync Server 2013 と Exchange 2013 の両方が使用されている環境でのみサポートされます。

  - Exchange 2010 上にメールボックスを持つユーザーは、常に、ユーザー写真のソースとして AD DS の**thumbnailPhoto**属性を使用します。

  - AD DS から**thumbnailPhoto**属性として保存されたユーザー写真は、外部/フェデレーションの連絡先に表示されません。

  - ユーザーの連絡先の写真が AD DS に保存されている場合、使用される画像ファイルは96×96ピクセルに制限され、100 KB のファイルサイズを超えないようにします。

  - Lync Server と Exchange Server の間の接続が失われた場合、AD DS からのユーザーの低解像度**thumbnailPhoto**が表示され、内部ユーザーのみになります。

  - アクティブなスピーカーでビデオが有効になっていない場合、高解像度のユーザー写真が Lync 2013 会議に表示されます。 また、ギャラリーのサムネイル写真の上にマウスポインターを移動すると、高解像度写真が表示されます。

</div>

<div>

## <a name="user-photos-in-lync-2010"></a>Lync 2010 のユーザーの写真

Lync 2010 クライアントでは、次の2つのオプションのいずれかを選択して、プロファイルの写真を表示したり、**既定の企業画像**を表示したり、 **web アドレスから画像を表示**したりすることができます。

<div>

## <a name="default-corporate-picture"></a>既定のコーポレート ピクチャ

[**既定の会社画像**] オプションを選択すると、Lync は Active Directory ドメインサービスから表示される写真を取得します。 使用されるイメージは、Active Directory ドメインサービスの**thumbnailPhoto**属性の値として定義されたイメージです。 これは、Exchange が Outlook で画像を表示するときに使用するファイルと同じです。

Active Directory ドメインサービスからイメージを使用する場合の考慮事項は次のとおりです。

  - 最大96ピクセル、96ピクセルの大きさの画像のみがサポートされます。 画像のファイルサイズは 100 KB に制限されています。

  - 既定では、ユーザーは**thumbnailPhoto**属性に使用されているイメージを変更できます。ただし、Lync クライアントを直接使用することはできません。 Active Directory ドメインサービスを使用してこれを無効にすることができます。

  - Active Directory ドメインサービスに保存された画像は、フェデレーションされた連絡先であっても、組織外の連絡先には表示されません。

  - 大規模な組織では、大量のユーザー用の画像を格納して取得することは、Active Directory ドメインサービスデータベースのサイズとパフォーマンスに影響することがあります。

  - 画像のサイズが制限され、ファイルのサイズが小さいため、低解像度の画像しか使用できません。

<div>

## <a name="how-users-manage-their-user-photos-in-active-directory-domain-services"></a>ユーザーが Active Directory ドメインサービスでユーザーの写真を管理する方法

ユーザーは、Lync 2010 クライアントを使用して、Active Directory ドメインサービスプロファイルで使用されているイメージを直接変更することはできません。 そのためには、次のいずれかのオプションを使用できます (使用可能な場合)。

  - **SharePoint Server**    ユーザーは、SharePoint サーバー上の [個人用サイト] に写真をアップロードし、 [sharepoint でプロファイルの同期を構成](https://go.microsoft.com/fwlink/p/?linkid=507466)して、Active Directory ドメインサービスの**thumbnailPhoto**属性に写真を同期させることができます。

  - **パブリックにアクセス可能な URL**     に保存された写真ユーザーは、使用するイメージに対して、公開されているアクセス可能な URL を指定してユーザーの写真を構成できます。 画像は、パスワードを使用せずに、一般にアクセス可能である必要があります。 指定した web アドレスに格納されているイメージは、プレゼンス情報の連絡先カードカテゴリを通じて他のユーザーに転送されます。 Lync クライアントがユーザーの写真を表示する必要がある場合は、指定された web アドレスから画像を取得します。

  - **Windows PowerShell**     の Exchange 2010 コマンドレット管理者は、 **thumbnailPhoto**属性を管理するために、の Exchange 2010 管理シェルで、[インポート-受信者データプロパティ](https://go.microsoft.com/fwlink/p/?linkid=507468)コマンドレットを実行できます。 Exchange 2010 コマンドレットを使用して画像をインポートする場合、ファイルのサイズは 10 KB に制限されます。

  - **サードパーティ製のツール**    ユーザーは自分の写真のみを**thumbnailPhoto**属性にアップロードできます。

</div>

</div>

<div>

## <a name="show-a-picture-from-a-web-address"></a>Web アドレスからピクチャを表示する

[ **Web アドレスから画像を表示**する] オプションを選択すると、入力したアドレスで画像が取得され、lync でユーザーの写真が表示されます。

Web アドレスから画像を使用する場合の考慮事項は次のとおりです。

  - ファイルサイズの制限は、[新しい-CsClientPolicy](https://go.microsoft.com/fwlink/p/?linkid=507463)コマンドレットで定義された、クライアントポリシーの**Maxphotosizekb**属性によって決定されます。 既定のサイズ制限は 30 KB です。 最大値は 100 KB です。 画像の解像度に制限はありませんが、サイズ制限を超える画像ファイルを使用しようとすると、Lync クライアントにダウンロードされません。 この値を0に設定すると、Lync でのすべてのユーザーの写真の使用を無効にすることができます。

  - Web アドレスからのユーザーの写真は、外部フェデレーションの連絡先に表示されます。

</div>

<div>

## <a name="managing-users-photo-with-client-policy-cmdlets"></a>クライアントポリシーコマンドレットを使用してユーザーの写真を管理する

Lync Server 2010 では、クライアントポリシー設定が CsClientPolicy コマンドレットを使用して構成されます。 構成済みのポリシー設定は、インバンドプロビジョニングを通じてクライアントに送信されます。 ユーザーの写真の表示を決定する CsClientPolicy コマンドレットの2つのパラメーターは、 **DisplayPhoto**と**Maxphotosizekb**です。 **DisplayPhoto**の対応するインバンドプロビジョニングパラメーターと**Maxphotosizekb**は、 **PhotoUsage**という名前です。 **PhotoUsage**パラメーターの値は、 **endpointConfiguration** **provisionGroup**を使用してクライアントに送信されます。 詳細については[、「クライアントポリシーと設定の概要](https://go.microsoft.com/fwlink/?linkid=507470)」を参照してください。

**DisplayPhoto**パラメーターの値は、ユーザーの写真の画像のソースを決定します。 次の表に、サポートされている値を示します。


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>DisplayPhoto パラメーターの値</th>
<th>画像ソース</th>
<th>Lync 2010 クライアントの設定</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>NoPhoto</p></td>
<td><p>なし</p></td>
<td><p><strong>マイ ピクチャを表示しない</strong></p></td>
</tr>
<tr class="even">
<td><p>PhotoFromADOnly</p></td>
<td><p>Active Directory</p></td>
<td><p><strong>既定のコーポレート ピクチャ</strong></p></td>
</tr>
<tr class="odd">
<td><p>AllPhotos</p></td>
<td><p>Web アドレス</p></td>
<td><p><strong>Web アドレスからピクチャを表示する</strong></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="how-lync-2010-client-gets-photos"></a>Lync 2010 クライアントが写真を取得する方法

Lync 2010 では、ユーザーの写真はアドレス帳サービスによってサーバー上で管理されます。 Lync クライアントは、最初にサーバーのアドレス帳 Web クエリ (ABWQ) サービスを照会することによってユーザーの写真を取得します。これは、配布リスト展開 web サービスを通じて公開されます。 クライアントはイメージファイルを受信し、ユーザーのキャッシュにコピーして、表示が必要になるたびにイメージをダウンロードしないようにします。 クエリから返される属性値も、ユーザーのキャッシュされたアドレス帳サービスエントリに格納されます。 アドレス帳サービスは、すべてのキャッシュされたイメージを24時間ごとに削除します。つまり、サーバー上のキャッシュで新しいユーザーイメージが更新されるまでに最大24時間かかる可能性があります。 [Update-csaddressbook](https://docs.microsoft.com/powershell/module/skype/Update-CsAddressBook)コマンドレットを使用して、キャッシュに強制的に更新することができます。

プレゼンス状態に含まれているユーザーの写真にも、Lync クライアントが使用できる新しい画像があるかどうかを判断するために使用するハッシュ値が関連付けられています。 プレゼンス状態で使用されるイメージファイルへの変更は、クライアントに自動的に通知されます。

<div class=" ">


> [!NOTE]  
> GalContacts データベースには写真が格納されていないため、ユーザーの写真をダウンロードすることは、クライアントポリシーの<STRONG>Addressbookavailability</STRONG>設定 (<A href="https://go.microsoft.com/fwlink/p/?linkid=507508">Set-csclientpolicy</A>) に依存しません。



</div>

ABWQ サービスへのクエリには、次の属性が含まれています。

  - **Photohash**    バイナリ写真データのハッシュ値。現在の写真が変更されたかどうかを判断するために使用されます。

  - **PhotoRelPath**    サーバーに保存されているイメージファイルへの相対パス。

  - **Photosize**    イメージファイルのサイズ (バイト単位)。

  - **タイムスタンプ**    イメージファイルが最後にサーバーからダウンロードされ、クライアントキャッシュにコピーされた日時。

次に、Lync 2010 クライアントは、イメージファイルを取得した後、クエリから返された属性値と、インバンドプロビジョニングからクライアントが受信した属性値を比較して、それらが異なるかどうかを確認します。 値が異なる場合、クライアントは、HTTP GET 要求を使用して、サインインしているユーザーのイメージファイルを取得します。

また、クライアントは、キャッシュされたバージョンのイメージファイルが作成された時点から、サーバーに対して24時間ごとにサーバーをチェックして、サーバー上の**Photohash**属性の値とクライアント上の値を比較します。 値が異なる場合、クライアントはイメージファイルが変更されたことを認識します。 更新されたイメージファイルを取得するために、クライアントは再び ABWQ サービスに対してクエリを実行し、サーバー上のイメージファイルでクライアントキャッシュ内のイメージファイルを更新します。これにより、クライアントキャッシュ内のファイルの**タイムスタンプ**もリセットされます。

以下に、ABWQ サービスへのクエリに対する応答の例を示します。
```xml
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
```

</div>

</div>

<div>

## <a name="user-photos-in-lync-2013"></a>Lync 2013 のユーザーの写真

Lync 2013 には、ユーザー写真の高解像度画像のサポートが導入されました。 Lync 2013 には、ユーザーの写真を Exchange 2013 上のユーザーのメールボックスに保存することもサポートされています。これにより、Lync 2010 に存在する画像の解像度とサイズの制限がなくなります。 Lync 2013 のユーザーの写真は最大で648ピクセルで、最大 20 MB のファイルサイズを持つ、648ピクセルにすることができます。 Lync 2013 の高解像度写真は、Exchange 2013 上のユーザーのメールボックスにある必要があり、Lync 2013 クライアントでのみサポートされています。 この統合 Exchange との統合により、Lync、Exchange、および SharePoint の2013バージョンに含まれる、Oauth という新しい認証フレームワークが利用されます。

展開で Exchange 2013 を使用していない場合、ユーザーの写真のサポートは Lync 2010 と同じです。 ただし、Lync 2013 クライアントでは、使用する写真を選択するためのユーザーオプションが異なります。 Lync 2013 クライアントでは、ユーザーは [**マイピクチャの非表示**] または [**マイピクチャの表示**] のどちらかを選択できます。 [ **Web サイトから画像を表示**する] オプションは既定では利用できませんが、クライアントポリシーを割り当てることによって有効にすることができます。

<div>

## <a name="hide-my-picture"></a>自分の写真を非表示にする

ユーザー写真の設定は、Lync 2013 の [**オプション**] ダイアログにあります。 **[自分の画像を表示**しない] を選択すると、lync クライアントにはユーザーの写真は表示されませんが、自分の写真は引き続き lync の外部の連絡先カードに表示されます。

</div>

<div>

## <a name="show-my-picture"></a>自分の写真を表示する

**[自分の画像を表示**する] オプションを選択すると、ユーザーの写真が lync クライアントおよび lync の会話の他のユーザーに表示されます。 使用されているイメージは、AD DS に格納されているものです。

</div>

<div>

## <a name="show-a-picture-from-a-website"></a>Web サイトから画像を表示する

[ **Web サイトから画像を表示**する] オプションは、クライアントポリシーを有効にするように設定した後、Lync 2013 で利用可能になります。 クライアントバージョンは、 [Lync 累積更新プログラム (2013 年11月](https://go.microsoft.com/fwlink/p/?linkid=509908)) でインストールされた15.0.4535.1002 よりも新しいバージョンである必要があります。 クライアントでの変更を確認するには、ユーザーは一度ログアウトしてから再度ログインする必要がある場合があります。

Lync Server 管理シェルで[set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy) policy を実行することによって、 **web サイトの設定から画像を表示**できるようにクライアントポリシーを設定することができます。 次のコマンドレットの例では、展開内のすべてのユーザーに対してグローバルにポリシーを設定する方法を示します。

   ```powershell
    $pe=New-CsClientPolicyEntry -Name EnablePresencePhotoOptions -Value True
   ```

   ```powershell
    $po=Get-CsClientPolicy -Identity Global
   ```

   ```powershell
    $po.PolicyEntry.Add($pe)
   ```

   ```powershell
    Set-CsClientPolicy -Instance $po
   ```


画像がユーザーのメールボックスにアップロードされると、Exchange によって、クライアントアプリケーションで使用できる画像の低解像度バージョンが自動的に作成されます。 ユーザー写真は、AD DS でも更新されます。

<div class=" ">


> [!NOTE]  
> AD DS でイメージファイルが更新されると、48 x 48 ピクセルのイメージが作成され、AD DS の thumbnailPhoto に使用されます。 既存のイメージは置き換えられます。 そのため、96 x 96 イメージを AD DS に追加した場合は、新しい 48 x 48 イメージで上書きされます。 これは、Lync 2010 クライアントを使用して、ユーザーが AD DS からユーザーの写真を取得するので、環境内にユーザーがいることです。 組織内に Lync 2010 クライアントがある場合は、96 x 96 ピクセルのイメージを、AD DS によって作成されたものと置き換えるようにインポートできます。



</div>

</div>

<div>

## <a name="user-photo-support-in-lync-2013"></a>Lync 2013 でのユーザーの写真のサポート

Lync 2013 では、次の表に示すように、ユーザーの写真に3つの画像解像度がサポートされています。 使用されるイメージは、Lync ユーザーに割り当てられているクライアントポリシー設定によって決まります。 詳細については、このトピックの「クライアントポリシーコマンドレットを使用してユーザーの写真を管理する」を参照してください。


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>画像解像度 (ピクセル)</th>
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
<td><p>Outlook Web App および Outlook 2013 で使用されます。</p></td>
</tr>
<tr class="odd">
<td><p>648 x 648</p></td>
<td><p>Lync 2013 デスクトップクライアントおよび Lync 2013 Web アプリで使用</p></td>
</tr>
</tbody>
</table>


Exchange 2013 でメールボックスが有効になっているすべてのユーザーは、Outlook Web Access または Lync 2013 クライアントオプションを使用して、高解像度写真を含む別のイメージをアップロードできます。 使用するイメージの推奨設定は次のとおりです。

  - **画像の解像度**    648 x 648 ピクセル

  - **色の深さ**    24ビット

  - **画像ファイルのサイズ**    最大 20 MB

  - **ファイル形式**    JPEG

648ピクセル×648ピクセルの一般的な24ビットの JPEG イメージはファイルサイズが約 240 KB なので、4ユーザーの写真ごとに 1 MB の保存スペースが必要になります。

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

