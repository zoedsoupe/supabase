# Supabase Elixir SDK

[![Hex.pm](https://img.shields.io/hexpm/v/supabase_potion.svg)](https://hex.pm/packages/supabase_potion)
[![Downloads](https://img.shields.io/hexpm/dt/supabase_potion.svg)](https://hex.pm/packages/supabase_potion)
[![Documentation](https://img.shields.io/badge/documentation-gray)](https://hexdocs.pm/supabase_potion)
[![lint](https://github.com/zoedsoupe/supabase/actions/workflows/lint.yml/badge.svg)](https://github.com/zoedsoupe/supabase/actions/workflows/lint.yml)
[![test](https://github.com/zoedsoupe/supabase/actions/workflows/test.yml/badge.svg)](https://github.com/zoedsoupe/supabase/actions/workflows/test.yml)

> Complete SDK and APIs integrations with Supabase

This monorepo houses the collection of Elixir SDK packages for integrating with Supabase, the open-source Firebase alternative. Our goal is to offer developers a seamless integration experience with Supabase services using Elixir.

## Packages Overview

- **Supabase Potion**: Main entrypoint for the Supabase SDK library, providing easy management for Supabase clients and connections. [Guide](./apps/supabase_potion/README.md).
- **Supabase Storage**: Offers developers a way to store large objects like images, videos, and other files. [Guide](./guides/storage.md)
- **Supabase PostgREST**: Directly turns your PostgreSQL database into a RESTful API using PostgREST. [Guide](#)
- **Supabase Realtime**: Provides a realtime websocket API, enabling listening to database changes. [Guide](#)
- **Supabase Auth**: A comprehensive user authentication system, complete with email sign-in, password recovery, session management, and more. [Guide](./apps/supabase_auth/README.md)
- **Supabase UI**: UI components to help build Supabase-powered applications quickly. [Guide](#)
- **Supabase Fetcher**: Customized HTTP client for making requests to Supabase APIs. [Guide](./guides/fetcher.md)

## Getting Started

### Installation

To install the base SDK:

```elixir
def deps do
  [
    {:supabase_potion, "~> 0.3"}
  ]
end
```

Then you can each package for the service you want to use. For example, if you want to use only the `Storage` integration:

```elixir
def deps do
  [
    {:supabase_potion, "~> 0.3"},
    {:supabase_storage, "~> 0.2"}
  ]
end
```

## Starting a Client

```elixir
iex> Supabase.Client.init_client!(%{conn: %{base_url: "<supa-url>", api_key: "<supa-key>"}, name: MyClient})
{:ok, #PID<0.123.0>}
```

For more information, refer to the [supabase_potion](./apps/supabase_potion/README.md) readme!

## Supabase Services

The Supabase Elixir SDK allows you to interact with various Supabase services:

### Supabase Storage

Supabase Storage is a service for storing large objects like images, videos, and other files. It provides a simple API with strong consistency, similar to AWS S3.

### Supabase PostgREST

PostgREST is a web server that turns your PostgreSQL database into a RESTful API. It automatically generates API endpoints and operations based on your database's structure and permissions.

### Supabase Realtime

Supabase Realtime offers a realtime WebSocket API powered by PostgreSQL notifications. You can use it to listen to changes in your database and receive updates instantly as they happen.

### Supabase Auth

Supabase Auth is a comprehensive user authentication system that includes features like email and password sign-in, email verification, password recovery, session management, and more, out of the box.

### Supabase UI

Supabase UI provides a set of UI components to help you build Supabase-powered applications quickly. It's built on top of Tailwind CSS and Headless UI, and it's fully customizable. The package even includes `Phoenix.LiveView` components!

### Supabase Fetcher

Supabase Fetcher is a customized HTTP client for Supabase, mainly used in Supabase Potion. It gives you complete control over how you make requests to any Supabase API.

## General Roadmap

If you want to track integration-specific roadmaps, check their own README.

- [x] Fetcher to interact with the Supabase API in a low-level way
- [x] Supabase Storage integration
- [ ] Supabase UI for Phoenix Live View
- [ ] Supabase Postgrest integration
- [x] Supabase Auth integration
- [ ] Supabase Realtime API integration


## Why another Supabase package?

Well, I tried to to use the [supabase-elixir](https://github.com/treebee/supabase-elixir) package but I had some strange behaviour and it didn't match some requirements of my project. So I started to search about Elixir-Supabase integrations and found some old, non-maintained packages that doesn't match some Elixir "idioms" and don't leverage the BEAM for a more integrated experience.

Also I would like to contribute to OSS in some way and gain more experience with the BEAM and HTTP integrations too. So feel free to not to use, give some counter arguments and also contribute to these packages!

## Credits & Inspirations

- [supabase-elixir](https://github.com/treebee/supabase-elixir)
- [storage-js](https://github.com/supabase/storage-js)

## Contributing

Contributions, issues, and feature requests are welcome! For major changes, please open an issue first to discuss what you would like to change.

## Acknowledgements

This SDK is a comprehensive representation of Supabase's client integrations. Thanks to the Supabase community for their support and collaboration.

## License

[MIT](LICENSE)

---

With the Supabase Elixir SDK, you have the tools you need to supercharge your Elixir applications by seamlessly integrating them with Supabase's powerful cloud services. Happy coding! 😄
