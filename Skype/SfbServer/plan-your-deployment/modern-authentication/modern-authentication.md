---
title: Skype for Business での先進認証についての計画
ms.reviewer: ''
ms.author: tracyp
author: MSFTTracyP
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 25e68396-96dc-4e4b-8a65-d30ea80d1bc9
description: 認証と承認 Skype の他の製品との統合を含め、ビジネス サーバーの計画に関するトピック
ms.openlocfilehash: 662eb90758bb22a9ef65492d9c9c1a99af778f23
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30873381"
---
# <a name="discussing-authentication-and-authorization-in-skype-for-business"></a>認証と承認 Skype のビジネスについて説明します。

認証と承認、関連する概念が (ただし、両方は、必要に応じて)、自動的に別の作業を実行します。 単純な用語で言えば、authenciation (認証) によって異なりますの機密情報だけで有効なユーザーを知っているが、およびパスワード、コード、指紋認証、証明書が true の場合、ユーザーに関するクレームの組み合わせまたは組み合わせこれらのものを一緒に使用することができます。 各種の認証は、確かに本人であることを証明するアウト プロセスです。

承認 (AuthZ) は、どのようなアクセスを持つユーザーを実証した後です。 どのような許可するようされて表示、編集、およびそれ以外の場合にアクセスすることを決定します。 などを SharePoint Online では、強力なサイト コレクションの管理者のアクセスする必要がありますが、ユーザーの問題のトラブルシューティングを行うの構成を変更する特権がある場合がありますのビジネス オンラインでは、Skype のように、別のオンライン ワークロードに切り替えた場合、サーバーまたはサーバー。 Exchange Online など、3 つ目のワークロードでは、平均的なユーザーのアクセスのみがあります。 AuthZ は、サービス/ワークロードで、アプリケーション、ファイル、およびその他のデータする必要があるどのようなどのくらいのアクセスを確認します。

例は、オンラインのプロパティ SharePoint とオンラインでの Exchange ですが、各種の認証および AuthZ のプロセスの作業、設置型と同様に、ハイブリッドの設置型では。 AAD を接続し、ad FS になるに関連する各種の認証および AuthZ ストーリーか、同期中、オンプレミス アカウントとパスワードをクラウドになどを最終的には、ツールの (である場合は、Office 365 または Azure Azure AD) AD の場合、または、AuthZ の流れに侵入します。頻繁に入力が不要、資格情報とシングル サインオンのシナリオを作成する、クラウドで作業負荷を切り替えるときです。 自身であるため、担当する各種の認証または AuthZ、整備士の一部のみはないです。

本日は、多くのテクノロジは、(認証および AuthZ) の 1 つのメカニズムでは、これらのプロセスを検討してください、認証プロセスにもそれらの承認を含む多くの事例を聞きます。 ユーザー アクセスの最初のステップであることを証明する本人は、各種の認証および AuthZ を使用することを確認するのにどのような彼または彼女へのアクセス (未処理の認証と OAuth が表示されます)、ユーザーは、ユーザーの知識を覚えておく必要があります。

  
## <a name="authentication-and-authorization-planning-topics"></a>認証および承認の計画のトピック

[How to use Modern Authentication (ADAL) with Skype for Business](plan-adal.md)

[Skype for Business topologies supported with Modern Authentication](topologies-supported.md)

[無効にする従来の認証方法内部と外部のネットワークを計画しています。](turn-on-modern-auth.md)

