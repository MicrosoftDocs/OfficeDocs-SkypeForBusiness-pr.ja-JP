---
title: Skype for Business Server で高解像度写真の使用を構成する
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 995da78a-dc44-45a3-908d-16fe36cfa0d9
description: '概要: Exchange Server 2019、Exchange Server 2016、Exchange Server 2013、Exchange Online および Skype for Business Server で高解像度写真の使用を構成します。'
ms.openlocfilehash: c55e5a90e222ea024dd63f72b26627141b2f113e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49834007"
---
# <a name="configure-the-use-of-high-resolution-photos-in-skype-for-business-server"></a>Skype for Business Server で高解像度写真の使用を構成する
 
**概要:** Exchange Server 2019、Exchange Server 2016、Exchange Server 2013、または Exchange Online と Skype for Business Server で高解像度写真の使用を構成します。
  
Skype for Business Server では、写真をユーザーの Exchange Server 2019、Exchange Server 2016、Exchange Server 2013、または Exchange Online メールボックスに格納できます。これにより、最大 648 ピクセル × 648 ピクセルの写真サイズが可能になります。 さらに、これらのExchange Server、必要に応じてさまざまな製品で使用するために、これらの写真のサイズを自動的に変更できます。 通常、次の 3 つの異なる写真のサイズと解像度を意味します。
  
- 64 × 64 ピクセル、Active Directory thumbnailPhoto 属性に使用されるサイズ。 Exchange Server に写真をアップロードすると、Exchange によってその写真の 64 ピクセル バージョンが自動的に作成され、ユーザーの thumbnailPhoto 属性が更新されます。 ただし、逆の点に注意してください。Active Directory の thumbnailPhoto 属性を手動で更新すると、ユーザーの Exchange メールボックス内の写真は自動的に更新されません。
    
- Microsoft Outlook 2013 Web App、Microsoft Outlook 2013、Skype for Business Web App、Skype for Business で使用する場合は、96 × 96 ピクセル。
    
- Skype for Business および Skype for Business Web App Skype for Business Web App で使用する 648 × 648 ピクセル。
    
> [!NOTE]
> リソースがある場合は、648 x 648 の写真をアップロードしてください。を使用して、任意のアプリケーションで最大解像度と最適な画像Office 2013します。 サイズが 648 x 648 で、深度が 24 ビットの JPEG の各写真のファイル サイズは約 240 キロバイトになります。 つまり、ユーザーの写真 4 枚ごとに約 1 MB のディスク領域が必要になります。 
  
Exchange Web サービスを使用してアクセスされる高解像度の写真は、Outlook 2013 Web App を実行しているユーザーがアップロードできます。ユーザーは自分の写真の更新のみを許可されます。 ただし、管理者は、Exchange 管理シェル と次のような一連の Windows PowerShell コマンドを使用して、すべてのユーザーの写真を更新できます。
  
```powershell
$photo = ([Byte[]] $(Get-Content -Path "C:\Photos\Kenmyer.jpg" -Encoding Byte -ReadCount 0))
Set-UserPhoto -Identity "Ken Myer" -PictureData $photo -Preview -Confirm:$False
Set-UserPhoto -Identity "Ken Myer" -Save -Confirm:$False
```

前の例の最初のコマンドでは、コマンドレットを使用してファイル ファイルの内容を読み取りC:\Photos\Kenmyer.jpg、そのデータを $photo という名前の変数に `Get-Content` 格納します。 2 番目のコマンドでは、Exchange コマンドレットを使用して写真をアップロードし、その写真を Ken Myer のユーザー アカウント `Set-UserPhoto` に添付します。
  
> [!NOTE]
> この例では、Ken Myer の Active Directory 表示名がユーザー アカウントの ID として使用されています。 また、その他の識別子 (ユーザーの SMTP アドレスやユーザー プリンシパル名など) を使用してユーザー アカウントを参照することもできます。 詳細については、Set-UserPhoto コマンドレットのドキュメント [https://go.microsoft.com/fwlink/p/?LinkId=268536](https://go.microsoft.com/fwlink/p/?LinkId=268536) を参照してください。
  
写真のアップロードは、その写真を Ken Myer のユーザー アカウントに割り当てる操作と同じではありません。写真のアップロードは、Outlook Web App の [オプション] ページに表示されるその写真のプレビューにすぎません。写真を実際にユーザー アカウントに割り当てるには、[オプション] ページの [**保存**] をクリックするか、例に示す 3 つ目のコマンドを管理者が実行する必要があります。3 つ目のコマンドでは、Save パラメーターを使用して写真を Ken Myer のユーザー アカウントに割り当てます。
  
```powershell
Set-UserPhoto -Identity "Ken Myer" -Save -Confirm:$False
```

新しい写真がユーザー アカウントに割り当てられているを確認するために、Ken Myer は Skype for Business にログオンし、[オプション] を選択して、[マイ ピクチャ] を **選択します**。 新しくアップロードされた写真が Ken の個人用の写真として表示されるはずです。 また、管理者が Internet Explorer を起動し、次のような URL にアクセスしてユーザーの写真を確認することもできます。
  
```console
https://atl-mail-001.litwareinc.com/ews/Exchange.asmx/s/GetUserPhoto?email=kenmyer@litwareinc.com&size=HR648x648
```

管理者が Internet Explorer を使用して写真を表示できるが、ユーザーが Skype for Business で自分の写真を表示できない場合は、Exchange Web サービスまたは Exchange 自動検出サービスとの接続に問題がある可能性があります。
  
また、この写真を Skype for Business で利用するために追加の構成は必要ありません。 代わりに、写真はアップロードされ、コマンドレットが実行された後すぐに `Set-UserPhoto` 利用できます。
