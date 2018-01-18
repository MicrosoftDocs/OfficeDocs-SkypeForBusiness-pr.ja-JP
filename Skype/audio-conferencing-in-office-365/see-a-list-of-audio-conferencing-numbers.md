---
title: "オーディオ会議の番号の一覧を参照してください。"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: 2d6b4ed4-e12b-4691-8405-fae720d69425
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business, Microsoft Teams
localization_priority: Normal
ROBOTS: None
f1keywords: None
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
description: "ビジネス用の Skype から、会議にダイヤルイン番号を検索する方法について説明します。 "
ms.openlocfilehash: 45e4dd113845c9c565162c4ef3047df83e1aeb43
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/15/2017
---
# <a name="see-a-list-of-audio-conferencing-numbers"></a>オーディオ会議の番号の一覧を参照してください。

設定するとオーディオ会議を Skype のビジネスおよびマイクロソフトのチームのユーザーに対して、オーディオ会議のために利用可能な電話番号を表示できます。 このリストには、すべての組織に利用可能な電話会議の電話番号があります。
  
 **価格を検索してください。** [オーディオ会議の価格](https://products.office.com/en-us/skype-for-business/audio-conferencing#Requirements)を参照してください。
  
> [!IMPORTANT]
> **オーディオ会議のすべてのダイヤルイン番号の一覧が含まれているリソースはありません。** かどうかダイヤルインの電話番号では、領域または国/地域を表示する検索する場合に、**ビジネス管理センターの Skype** > **音声** > **の電話番号**を**追加**] をクリックし、**新しいサービス番号**です。 **国/地域**、**状態の範囲のリストを使用して**、および検索をフィルター処理する**市区町村**です。 また、サービスのフリー ダイヤル番号を検索する場合は、**フリー ダイヤル**から**の状態または地域を選択**の一覧です。
  
1 つの電話番号が組織で使用可能な場合に適用されます既定の番号としてのすべてのユーザー。 複数の電話番号が利用できる場合は、ユーザーごとに既定の電話番号を選択します。 この既定の番号は、Skype でビジネスおよびマイクロソフトのチームの会議出席依頼に含まれます。
  
1 人のユーザーのダイヤルインの電話番号を変更するのには[携帯電話への招待に含まれている番号の設定](set-the-phone-numbers-included-on-invites.md)を確認できます。
  
> [!NOTE]
> 国内のダイヤルイン番号は専用の組織には、既定の電話番号として設定することが唯一のものです。 ただし、国際ダイヤルの番号は、複数の組織間で共有できます。 
  
## <a name="to-view-your-audio-conferencing-phone-numbers"></a>電話会議の電話番号を表示するのには

1. 職場または学校のアカウントを使用して、Office 365 にサインインします。
    
2. **Office 365 管理センター**を参照して > **ビジネス用の Skype**です。
    
3. **電話会議**には、**ビジネス管理センターの Skype**、左側のナビゲーションでの > **マイクロソフトのブリッジ**をし。
    
  - オーディオ会議で使用可能な電話番号を表示することができます。
    
  - 場所を表示することもでき、オーディオ会議で使用されるプライマリとセカンダリの言語の自動アテンダントです。
    
> [!NOTE]
> **オーディオ会議**に移動することができます > **ユーザー**と組織内の利用可能な番号の一覧から新しい番号を選択することによって番号の既定値を変更するのにはユーザーのプロパティ] を選択します。 [携帯電話への招待に含まれている番号の設定](set-the-phone-numbers-included-on-invites.md)を参照してください。 
  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Windows PowerShell で管理する方法

- 時間を短縮または、これを自動化するには、 [Get CsOnlineDialInConferencingServiceNumber](https://go.microsoft.com/fwlink/?LinkId=617691)コマンドレットを使用することができます。
    
- Windows PowerShell は、ユーザーを管理するユーザーを許可または許可されません。 Windows PowerShell を実行する複数のタスクがある場合、日常的な作業を簡素化する管理の単一ポイントを使用して Office 365 を管理できます。 Windows PowerShell を使い始めるには、以下のトピックを参照してください。
    
  - [Office 365 の PowerShell を使用する必要がある理由](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Windows PowerShell で Office 365 を管理するための最善の方法](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell には、実行しようとする設定の変更多くのユーザーを一度に 1 つなど、Office 365 管理センターを使用するだけでスピード、シンプルさと生産性に多くの利点があります。 次のトピックで、これらの利点について学習します。
    
  - [Windows PowerShell と Skype for Business Online の概要](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Windows PowerShell による Skype for Business Online の管理](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Windows PowerShell を使用した一般的な Skype for Business Online の管理タスクの実行](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > Skype for Business Online 用 Windows PowerShell モジュールでは、リモート Windows PowerShell セッションを作成して Skype for Business Online に接続できます。このモジュールは、64 ビットのコンピューターでのみサポートされ、Microsoft ダウンロード センターの「[Skype for Business Online 用 Windows PowerShell モジュール](https://go.microsoft.com/fwlink/?LinkId=294688)」からダウンロードできます。
  
## <a name="related-topics"></a>関連トピック

[Skype for Business および Microsoft Teams の電話会議のセットアップ](set-up-audio-conferencing.md)
  

