---
title: Skype for Business での先進認証についての計画
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
description: 他の製品との統合など、Skype for Business Server の認証と承認の計画トピック
ms.openlocfilehash: f732e4afa6b82554c4248a244276e5e5b60c71cc
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815845"
---
# <a name="discussing-authentication-and-authorization-in-skype-for-business"></a>Skype for Business での認証と承認について

認証と承認は関連する概念ですが、さまざまな作業を行います (ただし、どちらも必要です)。 単純な用語を使用する場合、authenciation (AuthN) は、有効なユーザーが知っているか、持っていることがわかっている、またはパスワード、コード、指紋、証明書、真であるユーザーに関するクレームの組み合わせ、またはそれらを組み合わせて使用した秘密によって異なります。 AuthN は、自分が言っていることを証明するためのプロセスです。

承認 (AuthZ) は、お客様の身元を証明した後にアクセス権を持っているかどうかに関係します。 表示、編集、その他のアクセスが許可されているものを特定します。 たとえば、SharePoint Online に対しては、サイトコレクション管理者による強力なアクセスが可能ですが、Skype for Business Online などのオンラインのワークロードに切り替えると、ユーザーの問題のトラブルシューティングを行うことができ、サーバーまたはサーバー。 Exchange Online などの3つ目のワークロードでは、平均ユーザーのアクセス権しか持たない場合があります。 AuthZ は、サービス/権限のロード、アプリケーション、ファイル、その他のデータに対してどの程度のアクセス権を付与するかを確認します。

この例には、SharePoint や Exchange online などのオンラインプロパティが含まれていますが、AuthN と AuthZ のプロセスはオンプレミスとハイブリッドの内部でも同じように動作します。 最終的には、AAD Connect や ADFS などのツールは、オンプレミスのアカウントとパスワードをクラウドの広告 (Office 365 または Azure の場合は Azure AD) に同期することによって、AuthN と AuthZ のストーリーに関与します。ユーザーは、資格情報の入力を頻繁に求められることはありません。たとえば、クラウドのワークロードを切り替えて、シングルサインオンシナリオを作成する場合です。 ただし、it 担当者は、it の一部ではなく AuthN または AuthZ を担当しています。

現在、多くのテクノロジでは、これらのプロセス (AuthN と AuthZ) が1つのメカニズムであると考えられ、認証プロセスへの参照には、承認も含まれています。 ユーザーアクセスの最初の手順は AuthN であり、自分の身元を証明していることを証明します。また、その AuthZ は、ユーザーがアクセス権を持つユーザー (Open Authorization または OAuth を使用して表示されます) についての情報を使用していることを覚えておくことが重要です。

  
## <a name="authentication-and-authorization-planning-topics"></a>認証と承認の計画に関するトピック

[How to use Modern Authentication (ADAL) with Skype for Business](plan-adal.md)

[Skype for Business topologies supported with Modern Authentication](topologies-supported.md)

[内部および外部のネットワークに対して従来の認証方法をオフにすることを計画しています。](turn-on-modern-auth.md)

