---
title: Microsoft Lync Server 2013 で高解像度写真を使用する構成
TOCTitle: Microsoft Lync Server 2013 で高解像度写真を使用する構成
ms:assetid: 995da78a-dc44-45a3-908d-16fe36cfa0d9
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ688150(v=OCS.15)
ms:contentKeyID: 49887065
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Microsoft Lync Server 2013 で高解像度写真を使用する構成

 

_**トピックの最終更新日:** 2016-12-08_

Microsoft Lync Server 2010 には、ユーザーが連絡先の写真を表示できる機能 (および自分の写真を他のユーザーに対して表示できる機能) が用意されていました。通常、このような写真は Active Directory にユーザーの thumbnailPhoto 属性の一部として保存されていました。これにより、写真のサイズと解像度が大きく制限されていました。thumbnailPhoto 属性で保持できるのは最大サイズが 48 × 48 ピクセルの写真のみです。

しかし、Microsoft Lync Server 2013 では、ユーザーの Microsoft Exchange Server 2013 メールボックスに写真を保存できます。そのため、最大 648 × 648 ピクセルのサイズの写真を使用できます。また、Exchange 2013 では、必要に応じて別の製品で写真を使用するために、写真のサイズを自動的に変更できます。通常、以下の 3 つの異なる写真サイズおよび解像度から選択できます。

  - 48 × 48 ピクセル。Active Directory の thumbnailPhoto 属性で使用されるサイズ。Exchange 2013 に写真をアップロードすると、Exchange ではその写真の 48 × 48 ピクセル バージョンを自動的に作成し、ユーザーの thumbnailPhoto 属性を更新します。ただし、逆の処理は行われません。つまり、Active Directory で thumbnailPhoto 属性を手動で更新しても、ユーザーの Exchange 2013 メールボックス内の写真は自動的に更新されません。

  - 96 × 96 ピクセル。Microsoft Outlook 2013 Web App、Microsoft Outlook 2013、Microsoft Lync Web App、および Lync 2013 で使用されるサイズ。

  - 648 × 648 ピクセル。Lync 2013 および Microsoft Lync Web App で使用されるサイズ。

> [!NOTE]
> リソースを確保できる場合は、648 × 648 の写真をアップロードすることをお勧めします。これにより、Office 2013 のどのアプリケーションにおいても最大の解像度と最適な写真の画質を実現できます。サイズが 648 × 648、ビットの深さが 24 の JPEG の写真の場合、ファイル サイズは約 240 KB になります。つまり、ユーザーの写真 4 枚ごとに約 1 MB のディスク容量が必要です。


Exchange Web サービスを使用してアクセスする高解像度の写真をアップロードできるのは、Outlook 2013 Web App を実行するユーザーです。ユーザーは自分の写真のみ更新できます。ただし、管理者は Exchange 管理シェルおよび次のような Windows PowerShell の一連のコマンドを使用して、ユーザーの写真を更新できます。

    $photo = ([Byte[]] $(Get-Content -Path "C:\Photos\Kenmyer.jpg" -Encoding Byte -ReadCount 0))
    Set-UserPhoto -Identity "Ken Myer" -PictureData $photo -Confirm:$False
    Set-UserPhoto -Identity "Ken Myer" -Save -Confirm:$False

上述の例の 1 つ目のコマンドは、Get-Content コマンドレットを使用して、C:\\Photos\\Kenmyer.jpg ファイルの内容を読み取って、そのデータを $photo 変数に保存します。2 つ目のコマンドでは、写真をアップロードして Ken Myer のユーザー アカウントにその写真を添付するために、Exchange の Set-UserPhoto コマンドレットが使用されます。

> [!NOTE]
> この例では、Ken Myer の Active Directory 表示名がユーザー アカウントの ID として使用されています。また、その他の識別子 (ユーザーの SMTP アドレスやユーザー プリンシパル名など) を使用してユーザー アカウントを参照することもできます。詳細については、Set-UserPhoto コマンドレットのドキュメント (<a href="http://go.microsoft.com/fwlink/?linkid=268536%26clcid=0x411" class="uri">http://go.microsoft.com/fwlink/?linkid=268536&amp;clcid=0x411</a>) を参照してください。


写真のアップロードは、その写真を Ken Myer のユーザー アカウントに割り当てる操作と同じではありません。写真のアップロードは、Outlook Web App の \[オプション\] ページに表示されるその写真のプレビューにすぎません。写真を実際にユーザー アカウントに割り当てるには、\[オプション\] ページの \[**保存**\] をクリックするか、例に示す 3 つ目のコマンドを管理者が実行する必要があります。3 つ目のコマンドでは、Save パラメーターを使用して写真を Ken Myer のユーザー アカウントに割り当てます。

    Set-UserPhoto -Identity "Ken Myer" -Save -Confirm:$False

新しい写真がユーザー アカウントに割り当てられたことを確認するには、Ken Myer が Lync 2013 にログオンして、\[**オプション**\]、\[**マイ ピクチャ**\] の順に選択します。新しくアップロードされた写真が Ken の個人用の写真として表示されるはずです。また、管理者が Internet Explorer を起動し、次のような URL にアクセスしてユーザーの写真を確認することもできます。

    https://atl-mail-001.litwareinc.com/ews/Exchange.asmx/s/GetUserPhoto?email=kenmyer@litwareinc.com&size=HR648x648

管理者が Internet Explorer を使用して写真を表示できるにもかかわらず、ユーザーが Lync 2013 で自分の写真を表示できない場合は、通常、Exchange Web サービスまたは Exchange 自動検出サービスに関する接続の問題があることを示しています。

Lync 2013 でこの写真を利用するために、構成を追加する必要はありません。写真がアップロードされて Set-UserPhoto コマンドレットを実行すると、即時に利用できるようになります。

