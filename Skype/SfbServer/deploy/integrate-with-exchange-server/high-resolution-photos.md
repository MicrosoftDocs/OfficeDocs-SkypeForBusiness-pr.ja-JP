---
title: Skype for Business Server での高解像度写真の使用を構成する
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
description: '概要: Exchange Server 2019、Exchange Server 2016、Exchange Server 2013、または Exchange Online および Skype for Business Server での高解像度写真の使用を構成します。'
ms.openlocfilehash: f5cc44f9f390c1d3241e7fae68054754ff7b0f76
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51109803"
---
# <a name="configure-the-use-of-high-resolution-photos-in-skype-for-business-server"></a>Skype for Business Server での高解像度写真の使用を構成する
 
**概要:** Exchange Server 2019、Exchange Server 2016、Exchange Server 2013、Exchange Online および Skype for Business Server での高解像度写真の使用を構成します。
  
Skype for Business Server では、写真をユーザーの Exchange Server 2019、Exchange Server 2016、Exchange Server 2013、または Exchange Online メールボックスに保存できます。これにより、最大 648 ピクセルの写真サイズを 648 ピクセル×648 ピクセルに設定できます。 さらに、必要にExchange Server異なる製品で使用するために、これらの写真のサイズを自動的に変更することもできます。 通常、次の 3 つの異なる写真サイズと解像度を意味します。
  
- 64 ピクセル × 64 ピクセル、Active Directory thumbnailPhoto 属性に使用されるサイズ。 写真を Exchange Server にアップロードすると、Exchange は自動的にその写真の 64 ピクセル バージョンで 64 ピクセルを作成し、ユーザーの thumbnailPhoto 属性を更新します。 ただし、この逆は true ではありません。Active Directory の thumbnailPhoto 属性を手動で更新した場合、ユーザーの Exchange メールボックスの写真は自動的には更新されません。
    
- 96 ピクセル ×96 ピクセル(Microsoft Outlook 2013 Web App、Microsoft Outlook 2013、Skype for Business Web App、Skype for Business で使用)。
    
- Skype for Business および Skype for Business Web App Skype for Business Web App で使用する場合は、648 ピクセル×648 ピクセル。
    
> [!NOTE]
> リソースがある場合は、648 x 648 の写真をアップロードしてください。任意のアプリケーションで最大解像度と最適な画質Office 2013します。 サイズが 648 x 648、深度が 24 ビットの各 JPEG 写真では、ファイル サイズは約 240 キロバイトになります。 つまり、ユーザー写真 4 枚ごとに約 1 メガバイトのディスク領域が必要になります。 
  
Exchange Web Services を使用してアクセスされる高解像度の写真は、Outlook 2013 Web App を実行しているユーザーがアップロードできます。ユーザーは自分の写真のみを更新できます。 ただし、管理者は、Exchange 管理シェルと次のような一連の Windows PowerShellコマンドを使用して、すべてのユーザーの写真を更新できます。
  
```powershell
$photo = ([Byte[]] $(Get-Content -Path "C:\Photos\Kenmyer.jpg" -Encoding Byte -ReadCount 0))
Set-UserPhoto -Identity "Ken Myer" -PictureData $photo -Preview -Confirm:$False
Set-UserPhoto -Identity "Ken Myer" -Save -Confirm:$False
```

前の例の最初のコマンドでは、コマンドレットを使用してファイルの内容を読み取り、C:\Photos\Kenmyer.jpg という名前の変数にデータ `Get-Content` を格納$photo。 2 番目のコマンドでは、Exchange コマンドレットを使用して写真をアップロードし、その写真を Ken Myer のユーザー アカウント `Set-UserPhoto` に添付します。
  
> [!NOTE]
> この例では、Ken Myer の Active Directory 表示名がユーザー アカウントの ID として使用されています。 また、その他の識別子 (ユーザーの SMTP アドレスやユーザー プリンシパル名など) を使用してユーザー アカウントを参照することもできます。 詳細については、Set-UserPhotoコマンドレットの [https://go.microsoft.com/fwlink/p/?LinkId=268536](/powershell/module/exchange/set-userphoto) ドキュメントを参照してください。
  
写真のアップロードは、その写真を Ken Myer のユーザー アカウントに割り当てる操作と同じではありません。写真のアップロードは、Outlook Web App の [オプション] ページに表示されるその写真のプレビューにすぎません。写真を実際にユーザー アカウントに割り当てるには、[オプション] ページの [**保存**] をクリックするか、例に示す 3 つ目のコマンドを管理者が実行する必要があります。3 つ目のコマンドでは、Save パラメーターを使用して写真を Ken Myer のユーザー アカウントに割り当てます。
  
```powershell
Set-UserPhoto -Identity "Ken Myer" -Save -Confirm:$False
```

新しい写真がユーザー アカウントに割り当てられているか確認するには、Ken Myer は Skype for Business にログオンし、[オプション] を選択し、[マイ ピクチャ] を **選択します**。 新しくアップロードされた写真が Ken の個人用の写真として表示されるはずです。 また、管理者が Internet Explorer を起動し、次のような URL にアクセスしてユーザーの写真を確認することもできます。
  
```console
https://atl-mail-001.litwareinc.com/ews/Exchange.asmx/s/GetUserPhoto?email=kenmyer@litwareinc.com&size=HR648x648
```

管理者が Internet Explorer を使用して写真を表示できますが、ユーザーが Skype for Business で自分の写真を表示できない場合は、Exchange Web Services または Exchange 自動検出サービスとの接続に問題がある可能性があります。
  
この写真を Skype for Business で使用するには、追加の構成は必要ありません。 代わりに、写真がアップロードされ、コマンドレットが実行された後、すぐに `Set-UserPhoto` 写真を利用できます。