---
title: Skype for Business Server で高解像度の写真を使用するように構成する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 995da78a-dc44-45a3-908d-16fe36cfa0d9
description: '概要: Exchange Server 2016 または Exchange Server 2013 および Skype for Business Server で高解像度の写真を使用するように構成します。'
ms.openlocfilehash: d52cdb2d84fedba0dcbec97cbca4074b1ae12a84
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34278207"
---
# <a name="configure-the-use-of-high-resolution-photos-in-skype-for-business-server"></a>Skype for Business Server で高解像度の写真を使用するように構成する
 
**概要:** Exchange Server 2016 または Exchange Server 2013 および Skype for Business Server で高解像度の写真の使用を構成します。
  
Skype for Business Server の写真は、ユーザーの Exchange Server 2016 または Exchange Server 2013 メールボックスに保存することができます。これにより、写真のサイズを648ピクセル、648ピクセルまでに設定できます。 また、必要に応じてさまざまな製品で使用するために、これらの写真のサイズを自動的に変更することもできます。 通常、3つの異なる写真のサイズと解像度を意味します。
  
- 64ピクセル x 64 ピクセル、Active Directory thumbnailPhoto 属性に使用されているサイズ。 Exchange Server に写真をアップロードすると、その写真の 64 64 ピクセルバージョンが自動的に作成され、ユーザーの thumbnailPhoto 属性が更新されます。 ただし、この逆のことはできないことに注意してください。 Active Directory の thumbnailPhoto 属性を手動で更新した場合、ユーザーの Exchange メールボックスの写真は自動的には更新されません。
    
- 96ピクセル x 96 ピクセル、Microsoft Outlook 2013 Web App、Microsoft Outlook 2013、Skype for Business Web App、Skype for Business で使用できます。
    
- skype for Business および skype for business web app の skype for business web App で使用するための648ピクセル x 648 ピクセル。
    
> [!NOTE]
> リソースがある場合は、648 x 648 の写真をアップロードすることをお勧めします。これにより、どの Office 2013 アプリケーションでも、最大解像度と最適な画質が提供されます。 各 JPEG 写真のサイズが 648 x 648 で、深度が24ビットの場合、ファイルサイズは約 240 kb となります。 つまり、4ユーザー写真ごとに約 1 mb のディスクスペースが必要になります。 
  
Exchange Web Services を使用してアクセスできる高解像度写真は、Outlook 2013 Web App を実行しているユーザーがアップロードできます。ユーザーは自分の写真を更新することのみ許可されています。 ただし、管理者は、Exchange 管理シェルと、次のような一連の Windows PowerShell コマンドを使用して、任意のユーザーの写真を更新することができます。
  
```
$photo = ([Byte[]] $(Get-Content -Path "C:\Photos\Kenmyer.jpg" -Encoding Byte -ReadCount 0))
Set-UserPhoto -Identity "Ken Myer" -PictureData $photo -Preview -Confirm:$False
Set-UserPhoto -Identity "Ken Myer" -Save -Confirm:$False
```

上の例の最初のコマンドでは`Get-Content` 、コマンドレットを使用して C:\Photos\Kenmyer.jpg ファイルの内容を読み取り、そのデータを $photo という名前の変数に格納しています。 2番目のコマンドでは、 `Set-UserPhoto` Exchange コマンドレットを使用して写真をアップロードし、その写真を Ken Myer のユーザーアカウントに添付します。
  
> [!NOTE]
> この例では、Ken Myer の Active Directory 表示名がユーザー アカウントの ID として使用されています。 また、その他の識別子 (ユーザーの SMTP アドレスやユーザー プリンシパル名など) を使用してユーザー アカウントを参照することもできます。 詳細[https://go.microsoft.com/fwlink/p/?LinkId=268536](https://go.microsoft.com/fwlink/p/?LinkId=268536)については、「Set-userphoto コマンドレットのドキュメント」を参照してください。
  
写真のアップロードは、その写真を Ken Myer のユーザー アカウントに割り当てる操作と同じではありません。写真のアップロードは、Outlook Web App の [オプション] ページに表示されるその写真のプレビューにすぎません。写真を実際にユーザー アカウントに割り当てるには、[オプション] ページの [**保存**] をクリックするか、例に示す 3 つ目のコマンドを管理者が実行する必要があります。3 つ目のコマンドでは、Save パラメーターを使用して写真を Ken Myer のユーザー アカウントに割り当てます。
  
```
Set-UserPhoto -Identity "Ken Myer" -Save -Confirm:$False
```

新しい写真がユーザーアカウントに割り当てられていることを確認するために、Ken Myer は Skype for Business にログオンし、[**オプション**] を選択してから、[**マイピクチャ**] を選択できます。 新しくアップロードされた写真が Ken の個人用の写真として表示されるはずです。 また、管理者が Internet Explorer を起動し、次のような URL にアクセスしてユーザーの写真を確認することもできます。
  
```
https://atl-mail-001.litwareinc.com/ews/Exchange.asmx/s/GetUserPhoto?email=kenmyer@litwareinc.com&amp;size=HR648x648
```

管理者が Internet Explorer を使って写真を表示できるが、ユーザーが Skype for Business で写真を表示できない場合は、Exchange Web Services または Exchange 自動検出サービスの接続に問題がある可能性があります。
  
この写真を Skype for Business で利用できるようにするために、追加の構成は必要ないことにご注意ください。 代わりに、アップロードされてから`Set-UserPhoto`コマンドレットが実行されると、写真はすぐに利用可能になります。
