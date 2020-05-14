---
title: Skype for Business での先進認証の計画
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
audience: ITPro
ms.topic: conceptual
manager: serdars
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 25e68396-96dc-4e4b-8a65-d30ea80d1bc9
description: 他の製品との統合を含む、Skype for Business Server の認証と承認の計画に関するトピック
ms.openlocfilehash: 3b673a9f88895ac57277ef51b51fe0a4a27c64a2
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221581"
---
# <a name="discussing-authentication-and-authorization-in-skype-for-business"></a>Skype for Business での認証と承認についての説明

認証と承認は関連する概念ですが、ユーザーにとってはさまざまな作業を行います。 単純な用語で記述された authenciation (認証) は、パスワード、コード、指紋、証明書、true であるユーザーについてのクレームの組み合わせ、またはこれらを組み合わせて使用することによって、パスワード、コード、指紋、証明書、またはこれらを組み合わせて使用することができます。 認証は、本人であることを証明するためのプロセスを実行します。

承認 (AuthZ) は、お客者の身元を確認した後にアクセス権を取得することに関係します。 表示、編集、またはその他のアクセスが許可されているかどうかを判断します。 たとえば、SharePoint Online に対するサイトコレクション管理者のアクセス権は強力ですが、Skype for Business Online などの他のオンラインワークロードに切り替えた場合、ユーザーの問題をトラブルシューティングする権限を持つことがあり、サーバーの構成を変更することはできません。 Exchange Online などの3番目のワークロードでは、平均的なユーザーのアクセス権しか持っていない可能性があります。 AuthZ は、サービス/アクセス負荷、アプリケーション、ファイル、およびその他のデータに対して、どの程度のアクセスが必要かを確認します。

この例では、SharePoint や Exchange online のようなオンラインプロパティを使用していますが、認証と AuthZ のプロセスはオンプレミスでもハイブリッドドでも同じ方法で動作します。 最終的には、AAD 接続や ADFS などのツールは、オンプレミスのアカウントとパスワードをクラウドの AD (Azure AD) に同期することによって、または intruding のフローでは、ユーザーが自分の資格情報の入力を求められることはありません。たとえば、クラウドのワークロードを切り替えるときにシングルサインオンのシナリオを作成する しかし、自分では、認証または承認の一部ではなく、そのメカニズムの一部ではありません。

現在、多くのテクノロジでは、これらのプロセス (認証と AuthZ) を1つのメカニズムと考えています。また、認証プロセスへの参照もいくつかあります。 ユーザーアクセスの最初のステップは認証であることを覚えておくことが重要です。これは、ユーザーが本人であることを確認し、そのユーザーがアクセス権を判断するユーザーの知識を利用することです (Open Authorization または OAuth を参照してください)。

  
## <a name="authentication-and-authorization-planning-topics"></a>認証と承認の計画に関するトピック

[Skype for Business での先進認証 (ADAL) の使用方法](plan-adal.md)

[先進認証でサポートされている Skype for Business のトポロジ](topologies-supported.md)

[従来の認証方法をネットワークの内部および外部にオフにする計画を立てます。](turn-on-modern-auth.md)

