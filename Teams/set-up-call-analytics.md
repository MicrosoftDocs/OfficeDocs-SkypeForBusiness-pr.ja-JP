---
title: 通話分析をセットアップする
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.reviewer: mikedav, wlooney
ms.topic: article
ms.assetid: fbf7247a-84ae-46cc-9204-2c45b1c734cd
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
search.appverid: MET150
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Reporting
description: Skype for Business および Microsoft Teams の通話品質の問題を特定してトラブルシューティングするために通話分析をセットアップして使用します。
ms.openlocfilehash: ff413cf0f708f14feb8aa154be0dd4229e36eed5
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34305222"
---
# <a name="set-up-call-analytics"></a>通話分析をセットアップする

チームまたは Skype for Business Online 管理者は、通話分析を使用して、Skype for Business および Microsoft Teams の通話品質と接続の問題のトラブルシューティングを行うことができます。 通話分析では、次の機能を設定すると便利です。
  
- ヘルプデスクエージェントなどの他のユーザーが通話分析を使用して、Microsoft Teams 管理センターの他のユーザーにアクセスできないようにするアクセス許可を設定します。 
    
- .Tsv または .csv データファイルをアップロードすることにより、建物、サイト、テナント情報を通話分析に追加します。
    
**通話分析は Microsoft Teams 管理センターで利用できるようになりました**。 すべての通話情報とユーザーのデータを表示するには、[**通話履歴**] タブを使用します。これを行うには、次のいずれかの操作を行って、ユーザーのプロファイルページを参照します。

- ダッシュボードからユーザーを検索します。
  
   ![ダッシュボードでのユーザー検索のスクリーンショット](media/set-up-call-analytics-image-1.png)

-  左側のナビゲーションで [**ユーザー** ] を選択します。

   ![左側のナビゲーションのスクリーンショット](media/set-up-call-analytics-image-2.png)
  
## <a name="set-call-analytics-permissions"></a>通話分析のアクセス許可を設定する
<a name="BKMK_SetCAPerms"></a>

管理者は、通話分析のすべての機能にフルアクセスできます。 また、サポートスタッフに Azure Active Directory ロールを割り当てることもできます。 通話分析の限定されたビューが必要なユーザーにチーム通信のサポートスペシャリストの役割を割り当てます。 通話分析の全機能にアクセスする必要があるユーザーに、Teams 通信サポートエンジニアの役割を割り当てます。 どちらの権限レベルでも、Microsoft Teams 管理センターの残りの部分にはアクセスできません。

> [!NOTE]
> 通信サポートスペシャリストの役割は、tier 1 のサポートと同等であり、通信サポートエンジニアの役割は tier 2 サポートと同等です。

Teams の管理者ロールの詳細については、「 [Microsoft teams の管理者ロールを使用してチームを管理する](using-admin-roles.md)」を参照してください。 
  
通信サポートの専門家が、基本的な通話品質の問題を処理します。 会議の問題を調査することはありません。 代わりに、関連情報を収集し、コミュニケーションサポートエンジニアにエスカレートします。 通信サポートエンジニアは、コミュニケーションサポートスペシャリストから非表示になっている詳細な通話ログに情報を表示します。 次の表では、通話分析を使用している場合の通信サポートスペシャリストと通信サポートエンジニアが利用できる情報の概要を示します。

|**処理**|**通話分析の情報**|**コミュニケーションサポートスペシャリストが表示する内容**|**通信サポートエンジニアが見ることができる内容**|
|:-----|:-----|:-----|:-----|
|**通話** <br/> |発信者の名前  <br/> |エージェントが検索したユーザーの名前のみ。  <br/> |ユーザー名。  <br/> |
||受信者の名前  <br/> |内部ユーザーまたは外部ユーザーとして表示されます。  <br/> |受信者の名前。  <br/> |
||発信者の電話番号  <br/> |最後の3桁を除くすべての電話番号は、アスタリスク記号で隠蔽されています。 たとえば、15552823 * * * とします。  <br/> |最後の3桁を除くすべての電話番号は、アスタリスク記号で隠蔽されています。 たとえば、15552823 * * * とします。  <br/> |
||受信者の電話番号  <br/> |最後の3桁を除くすべての電話番号は、アスタリスク記号で隠蔽されています。 たとえば、15552823 * * * とします。  <br/> |最後の3桁を除くすべての電話番号は、アスタリスク記号で隠蔽されています。 たとえば、15552823 * * * とします。  <br/> |
||**** > **[** 通話の詳細] タブ <br/> |情報は表示されません。  <br/> |デバイス名、IP アドレス、サブネットマッピングなど、すべての詳細が表示されます。  <br/> |
||**[通話の詳細** > ] の **[詳細** > **デバッグ**] タブ <br/> |情報は表示されません。  <br/> |DNS サフィックスや SSID などのすべての詳細が表示されます。  <br/> |
|**会議** <br/> |参加者名  <br/> |エージェントが検索したユーザーの名前のみ。 内部ユーザーまたは外部ユーザーとして識別された他の参加者。  <br/> |すべての名前が表示されます。  <br/> |
||参加者数  <br/> |参加者の数。  <br/> |参加者の数。  <br/> |
||セッションの詳細  <br/> |例外と共に表示されるセッションの詳細。 エージェントで検索されたユーザーの名前のみが表示されます。 内部ユーザーまたは外部ユーザーとして識別された他の参加者。 アスタリスク記号が付いた、電話番号の最後の3桁が隠蔽されています。  <br/> |セッションの詳細が表示されます。 ユーザー名とセッションの詳細が表示されます。 アスタリスク記号が付いた、電話番号の最後の3桁が隠蔽されています。  <br/> |
||||
   
 ### <a name="set-up-permissions-by-assigning-admin-roles"></a>管理者ロールを割り当ててアクセス許可を設定する
<a name="BKMK_SetUpTier"> </a>

Azure Active Directory に管理者ロールを割り当てる方法については、「 [Azure Active directory での役割の表示と割り当て](https://docs.microsoft.com/en-us/azure/active-directory/users-groups-roles/directory-manage-roles-portal)」を参照してください。

## <a name="upload-a-tsv-or-csv-file-to-add-building-site-and-tenant-information"></a>.Tsv または .csv ファイルをアップロードして、建物、サイト、テナントの情報を追加する
<a name="BKMK_UploadFiles"> </a>

.Csv または .tsv ファイルをアップロードすることにより、建物、サイト、テナント情報を追加することができます。 すべての情報を使って、通話分析で IP アドレスを物理的な場所に対応付けることができます。 この情報は、お客様またはヘルプデスクの担当者が、通話の問題の傾向を見つけるのに役立ちます。 たとえば、同じ建物内の多くのユーザーが同様の通話品質の問題を抱えているのはなぜですか? 

チームと Skype for business の管理者である場合は、Teams & Skype for Business 通話品質ダッシュボードの既存のデータファイルを使用できます。 まず、通話品質ダッシュボードからファイルをダウンロードしてから、それをアップロードして分析を呼び出します。 

- 既存のデータファイルをダウンロードするには、 **Microsoft Teams 管理センター** > の**通話品質ダッシュボード** > **で今すぐアップロード**します。 [**マイアップロード**] ボックスの一覧で、目的のファイルの横にある [**ダウンロード**] をクリックします。

- 新しいファイルをアップロードするには、 **Microsoft Teams 管理センター** > の**場所**に移動し、[**場所データのアップロード**] または [場所のデータの**置き換え**] を選択します。
  
.Tsv または .csv ファイルを最初から作成する場合は、「[テナントデータファイルの形式と建物データファイルの構造](turning-on-and-using-call-quality-dashboard.md#BKMKTenantDataFile)」を参照してください。
  
## <a name="related-topics"></a>関連トピック
<a name="BKMK_UploadFiles"> </a>

[通話分析を使用して低品質の通話をトラブルシューティングする](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[通話分析および通話品質ダッシュボード](difference-between-call-analytics-and-call-quality-dashboard.md)

  
 
