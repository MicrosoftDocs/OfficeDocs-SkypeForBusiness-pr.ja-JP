---
title: デバイス ログ構成の編集
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.ClientDeviceUpdateEdit
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: e534e6a5-fb3e-40b1-a189-fce64c42f512
description: '[編集 ログ設定] ページでは、最大ログ キャッシュ サイズ、最大ログ ファイル サイズ、またはログ ファイルを削除するまでに保持する期間を指定するデバイス ログ構成を追加できます。 これらの設定は、組織の要件に従って変更できます。'
ms.openlocfilehash: 6e6278fb44344b99f018f297ecdd1494df846730
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/08/2021
ms.locfileid: "60835545"
---
# <a name="device-log-configuration-edit"></a>デバイス ログの構成: 編集
 
[**編集 ログ設定**] ページでは、最大ログ キャッシュ サイズ、最大ログ ファイル サイズ、またはログ ファイルを削除するまでに保持する期間を指定するデバイス ログ構成を追加できます。 これらの設定は、組織の要件に従って変更できます。
  
> [!CAUTION]
> ファイルを削除すると、それらはファイル システムから完全に削除されます。 ファイルを削除した後、ファイルを復旧することはできません。 
  
## <a name="tasks-you-can-perform"></a>実行できるタスク

[**編集 ログ設定**] ページでは、次のタスクを実行できます。
  
- デバイス ログ構成をグローバルに、または特定のサイトに追加します。
    
- 既存のデバイス ログ構成のオプションを変更します。
    
## <a name="ui-reference"></a>UI リファレンス

次の一覧に、このページのメニュー、コマンド、フィールド、およびプロパティを示します。
  
- **スコープ** デバイス ログ構成のスコープ (グローバルまたはサイト) を識別します。
    
- **名前** デバイス ログ構成の名前を追加または変更できます。
    
- **最大ファイル サイズ (バイト)** ログ ファイルが削除される前の最大サイズを指定できます。 既定値は 1,024,000 バイト (1 MB) です。
    
- **最大キャッシュ サイズ (バイト)** キャッシュをクリアし、データをログ ファイルに書き込む前に、ログ ファイル キャッシュに保持できる最大情報量 (バイト単位) を指定できます。 既定値は 512,000 バイト (0.5 MB) です。
    
- **キャッシュをフラッシュする分 (1 ~ 60)** ログ ファイル キャッシュに格納されている情報が実際のログ ファイルに書き込まれる頻度を指定できます。 データがログに記録された後、キャッシュはクリアされます。 既定値は 5 分です。
    
- **ログ ファイルを保持する日数 (1 ~ 365)** ログ ファイルが削除される前に保持される日数を指定できます。 既定値は 10 日です。
    
## <a name="see-also"></a>関連項目

[デバイス ログの構成](device-log-configuration.md)
