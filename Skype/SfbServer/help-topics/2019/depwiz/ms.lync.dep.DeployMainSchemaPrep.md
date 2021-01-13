---
title: スキーマの準備
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: Active Directory ドメイン サービスのスキーマを準備するには、Skype for Business Server 展開ウィザードでスキーマの準備手順を実行します。 [実行] をクリックしてスキーマの準備を開始します。
ms.openlocfilehash: b666cda29267c6f74eb034389f3f7967d7af99c5
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49833777"
---
# <a name="prepare-schema"></a>スキーマの準備
 
Active Directory ドメイン サービスのスキーマを準備するには、Skype for Business Server 展開ウィザードでスキーマの準備手順を実行します。 **[実行]** をクリックしてスキーマの準備を開始します。 スキーマの準備手順では、展開ウィザードが実行されているシステムの \Program Files\Skype for Business Server 2019\Deployment\Setup ディレクトリにある指定されたスキーマ定義ファイルを読み取ります。 これらのファイルは、インストール メディアの \Support\Schema ディレクトリにもあります。 [スキーマの準備] 手順では、スキーマを拡張し、プロセスの状態を報告します。 また、プロセスが完了したことも通知します。 概要画面では、プロセスのログを表示できます。 ログを調べ、正常に準備が完了したことを確認してください。
  
> [!IMPORTANT]
> スキーマを拡張するには、Schema Admins グループおよび Enterprise Admins グループのメンバーとしてドメインにログインする必要があります。 
  
クラスと属性が追加され、Active Directory ドメイン サービス スキーマが拡張され、Skype for Business Server サーバー、サービス、およびユーザー オブジェクトがサポートされます。 スキーマを拡張する前に、スキーマ マスター役割を持つドメイン コントローラーのシステム状態バックアップを行ってください。 
  
> [!CAUTION]
> スキーマの拡張は元に戻すことはできません。 スキーマ拡張が失敗した場合の潜在的な影響を抑制するためにあらゆる手段を講じ、スキーマの拡張が成功するようにしてください。 これは、通信が途絶えた場合や、サーバーでその他の障害が発生した場合には特に重要です。 スキーマ マスター ドメイン コントローラーのバックアップと Active Directory の完全バックアップを実行する必要があります。 
  
スキーマ マスター ドメイン コントローラーのバックアップと Active Directory の完全バックアップを実行するには、次の手順を実行します。
  
1. スキーマ マスター役割を持つドメイン コントローラーをネットワークから切断します。
    
2. スキーマ マスターを保持するドメイン コントローラーのシステム状態バックアップを実行します。
    
3. スキーマを拡張します。
    
4. スキーマを正常に拡張できたら、ドメイン コントローラーをネットワークに再接続し、レプリケーションがアクティブで機能していることを確認します。
    
5. スキーマ拡張機能が失敗する可能性が低い場合は、以前に行ったシステム状態のバックアップを使用して、ドメイン コントローラーと Active Directory のシステム状態を復元します。
    
> [!NOTE]
> Skype for Business Server 展開ウィザードによって作成されたログ ファイルを確認する必要がある場合は、展開ウィザードが実行されたコンピューター上の手順を実行した Active Directory ユーザーの Users ディレクトリにファイルがあります。 たとえば、ユーザーがドメイン Contoso.net でドメイン管理者としてログインした場合、ログ ファイルは C:\Users\Administrator.Contoso\AppData\Local\Temp にあります。 
  

