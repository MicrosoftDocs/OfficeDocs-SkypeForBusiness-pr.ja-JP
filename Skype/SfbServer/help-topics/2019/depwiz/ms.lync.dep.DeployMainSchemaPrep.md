---
title: スキーマの準備
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeployMainSchemaPrep
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 337aa234-c5f3-4468-a047-2023848e942c
ROBOTS: NOINDEX, NOFOLLOW
description: Active Directory ドメインサービスのスキーマを準備するには、Skype for Business Server 展開ウィザードでスキーマの準備手順を実行します。 [実行] をクリックしてスキーマの準備を開始します。
ms.openlocfilehash: c7a9529112aace5199a45c9556d3756a940fba95
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41794806"
---
# <a name="prepare-schema"></a>スキーマの準備
 
Active Directory ドメインサービスのスキーマを準備するには、Skype for Business Server 展開ウィザードでスキーマの準備手順を実行します。 [**実行**] をクリックしてスキーマの準備を開始します。 [スキーマの準備] 手順では、展開ウィザードが実行されているシステム上の Files\Skype ディレクトリで、提供されているスキーマ定義のファイルを読み取ります。 これらのファイルは、インストール メディアの \Support\Schema ディレクトリにもあります。 [スキーマの準備] 手順では、スキーマを拡張し、プロセスの状態を報告します。 また、プロセスが完了したことも通知します。 概要画面では、プロセスのログを表示できます。 ログを調べ、正常に準備が完了したことを確認してください。
  
> [!IMPORTANT]
> スキーマを拡張するには、Schema Admins グループおよび Enterprise Admins グループのメンバーとしてドメインにログインする必要があります。 
  
クラスと属性を追加して、Skype for Business Server server、サービス、ユーザーオブジェクトをサポートするように Active Directory ドメインサービススキーマを拡張します。 スキーマを拡張する前に、スキーママスターの役割を保持しているドメインコントローラーのシステム状態のバックアップを取得する必要があります。 
  
> [!CAUTION]
> スキーマの拡張は元に戻すことはできません。 スキーマ拡張が失敗した場合の潜在的な影響を抑制するためにあらゆる手段を講じて、スキーマの拡張が成功するようにしてください。 これは、通信が途絶えた場合や、サーバーでその他の障害が発生した場合には特に重要です。 スキーママスタードメインコントローラーのバックアップを実行し、Active Directory の完全なバックアップを行う必要があります。 
  
スキーママスタードメインコントローラーのバックアップ、および Active Directory の完全なバックアップを実行するには、次の手順を実行します。
  
1. スキーマ マスターの役割を持つドメイン コントローラーをネットワークから切断します。
    
2. スキーマ マスターを保持するドメイン コントローラーのシステム状態のバックアップを実行します。
    
3. スキーマを拡張します。
    
4. スキーマを正常に拡張できたら、ドメイン コントローラーをネットワークに再接続し、レプリケーションがアクティブで機能していることを確認します。
    
5. スキーマの拡張エラーが発生した場合は、前に行ったシステム状態のバックアップを使用して、ドメインコントローラーと Active Directory のシステム状態を復元します。
    
> [!NOTE]
> Skype for Business Server Deployment ウィザードによって作成されたログファイルを確認する必要がある場合は、展開ウィザードが実行されたコンピューター上のファイルを、手順を実行した Active Directory ユーザーの Users ディレクトリで見つけることができます。 たとえば、ユーザーがドメイン Contoso.net のドメイン管理者としてログインしている場合、ログファイルは C:\Users\Administrator.Contoso\AppData\Local\Temp にあります。 
  

