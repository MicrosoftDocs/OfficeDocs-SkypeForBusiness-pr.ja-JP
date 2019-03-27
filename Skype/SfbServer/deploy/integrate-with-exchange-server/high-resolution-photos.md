---
title: ビジネス サーバー用の Skype の高解像度の写真の使用を構成します。
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 12/20/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 995da78a-dc44-45a3-908d-16fe36cfa0d9
description: '概要: ビジネス サーバーの 2016 の Exchange Server や Exchange Server 2013 と Skype の高解像度の写真の使用を構成します。'
ms.openlocfilehash: 56fef2cfa8c62a66698c2232c9273cdb5604b5b8
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30875434"
---
# <a name="configure-the-use-of-high-resolution-photos-in-skype-for-business-server"></a>ビジネス サーバー用の Skype の高解像度の写真の使用を構成します。
 
**の概要:** 2016 の Exchange Server や Exchange Server 2013 と Skype のビジネス サーバーの高解像度の写真の使用を構成します。
  
ビジネス サーバーの Skype では、メールボックスの [ユーザーの 2016 の Exchange Server や Exchange Server 2013 できる写真のサイズの最大の 648 648 ピクセル ピクセル写真を格納できます。 さらに、Exchange Server に自動的にサイズを変更できますこれらの写真のさまざまな製品で使用するため必要に応じて。 通常次の 3 つの別の写真のサイズおよび解像度を意味します。
  
- 64 × 64 ピクセル、thumbnailPhoto の Active Directory 属性を使用するサイズです。 Exchange Server に写真をアップロードする場合 Exchange が自動的にその写真の 64 ピクセルのバージョンで 64 ピクセルを作成およびユーザーの thumbnailPhoto の属性を更新します。 ただし、逆は真ではありません: Active Directory 内の thumbnailPhoto 属性を手動で更新する場合は、ユーザーの Exchange メールボックスにある写真に自動的に更新されません。
    
- Microsoft Outlook 2013 の Web アプリケーション、Microsoft Outlook 2013、Skype のビジネス Web アプリケーション、およびビジネス用の Skype で使用するための 96 ピクセルで 96 ピクセルです。
    
- 648 648 のピクセルのピクセルを使用して、Skype のビジネスおよび Skype のビジネス Web アプリケーションの Skype のビジネス Web アプリケーションの。
    
> [!NOTE]
> リソースがある場合は、648 648 x 画像をアップロードすることをお勧め最大解像度と任意の Office 2013 アプリケーションで最適な画質を提供します。 648 648 x のサイズと深さが 24 ビットの JPEG 写真のそれぞれは、約 240 キロバイトのファイルのサイズになります。 つまり、すべての 4 つのユーザーの写真の約 1m バイトのディスク領域が必要です。 
  
Outlook 2013 Web アプリケーションを実行しているユーザーが Exchange Web サービスを使用してアクセスされる、高解像度の写真をアップロードします。自分の写真を更新するのには許可されているだけです。 ただし、管理者は、Exchange 管理シェルは、一連の Windows PowerShell コマンドを次のようなを使用してすべてのユーザーの写真を更新できます。
  
```
$photo = ([Byte[]] $(Get-Content -Path "C:\Photos\Kenmyer.jpg" -Encoding Byte -ReadCount 0))
Set-UserPhoto -Identity "Ken Myer" -PictureData $photo -Preview -Confirm:$False
Set-UserPhoto -Identity "Ken Myer" -Save -Confirm:$False
```

前の例の最初のコマンドを使用して、 `Get-Content` $photo という名前のコマンドレットには、C:\Photos\Kenmyer.jpg ファイルの内容を読むし、そのデータを変数に格納します。 2 番目のコマンドでは、Exchange コマンドレットの`Set-UserPhoto`を使用して写真をアップロードし、Ken Myer のユーザー アカウントにその写真を添付します。
  
> [!NOTE]
> この例では、Ken Myer の Active Directory 表示名がユーザー アカウントの ID として使用されています。 また、その他の識別子 (ユーザーの SMTP アドレスやユーザー プリンシパル名など) を使用してユーザー アカウントを参照することもできます。 セット UserPhoto コマンドレットのドキュメントを参照してください[https://go.microsoft.com/fwlink/p/?LinkId=268536](https://go.microsoft.com/fwlink/p/?LinkId=268536)の詳細について
  
写真のアップロードは、その写真を Ken Myer のユーザー アカウントに割り当てる操作と同じではありません。写真のアップロードは、Outlook Web App の [オプション] ページに表示されるその写真のプレビューにすぎません。写真を実際にユーザー アカウントに割り当てるには、[オプション] ページの [**保存**] をクリックするか、例に示す 3 つ目のコマンドを管理者が実行する必要があります。3 つ目のコマンドでは、Save パラメーターを使用して写真を Ken Myer のユーザー アカウントに割り当てます。
  
```
Set-UserPhoto -Identity "Ken Myer" -Save -Confirm:$False
```

新しい写真がユーザー アカウントに割り当てられていることを確認するには、Ken Myer にログオンできる Skype のビジネス、**オプション**の選択]、および [**マイ ピクチャ**。 新しくアップロードされた写真が Ken の個人用の写真として表示されるはずです。 また、管理者が Internet Explorer を起動し、次のような URL にアクセスしてユーザーの写真を確認することもできます。
  
```
https://atl-mail-001.litwareinc.com/ews/Exchange.asmx/s/GetUserPhoto?email=kenmyer@litwareinc.com&amp;size=HR648x648
```

管理者は、Internet Explorer を使用して写真を表示できますが、ユーザーは、ビジネスの Skype で自分の写真を表示できない場合は、Exchange Web サービスまたは Exchange 自動検出サービス接続の問題がある可能性があります。
  
またビジネス用の Skype でこの写真を利用するのには追加構成は必要ないことです。 代わりに、写真すぐが表示されますが、アップロードされた後、および`Set-UserPhoto`コマンドレットが実行されています。
