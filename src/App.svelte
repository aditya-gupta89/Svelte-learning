<script>
  import Header from "./UI/Header.svelte";
  import Meetup from "./Meetup/Meetup.svelte";
  import TextInput from "./UI/TextInput.svelte";
  import Button from "./UI/Button.svelte";
  let meetups = [
    {
      id: "m1",
      title: "Coding Bootcamp",
      subtitle: "Learn to code in 2 hours",
      description:
        "In this meetup, we will have some experts that teach you how to code!",
      imageUrl:
        "https://upload.wikimedia.org/wikipedia/commons/thumb/9/9a/Caffe_Nero_coffee_bar%2C_High_St%2C_Sutton%2C_Surrey%2C_Greater_London.JPG/800px-Caffe_Nero_coffee_bar%2C_High_St%2C_Sutton%2C_Surrey%2C_Greater_London.JPG",
      address: "27th Nerd Road, 32523 New York",
      contactEmail: "code@test.com",
    },
    {
      id: "m2",
      title: "Swim Together",
      subtitle: "Let's go for some swimming",
      description: "We will simply swim some rounds!",
      imageUrl:
        "https://upload.wikimedia.org/wikipedia/commons/thumb/6/69/Olympic_swimming_pool_%28Tbilisi%29.jpg/800px-Olympic_swimming_pool_%28Tbilisi%29.jpg",
      address: "27th Nerd Road, 32523 New York",
      contactEmail: "swim@test.com",
    },
  ];
  let title = "";
  let subTitle = "";
  let description = "";
  let email = "";
  let address = "";
  let imageUrl = "";
  const handlesubmit = () => {
    let meetup = {
      id: Math.random().toString(),
      title: title,
      subtitle: subTitle,
      description: description,
      imageUrl: imageUrl,
      address: address,
      contactEmail: email,
    };
    console.log(meetup)
    meetups = [...meetups, meetup];
  };
</script>

<Header />

<main>
  <form on:submit|preventDefault={handlesubmit}>
    <TextInput
      rows={0}
      value={title}
      type="text"
      on:input={(event) => (title = event.target.value)}
      id="title"
      label="Title"
      placeholder="Please enter a Title"
    />
    <TextInput
      rows={0}
      value={subTitle}
      on:input={(event) => (subTitle = event.target.value)}
      type="text"
      id="subTitle"
      label="SubTitle"
      placeholder="Please enter a SubTitle"
    />
    <TextInput
      rows={0}
      value={imageUrl}
      on:input={(event) => (imageUrl = event.target.value)}
      type="text"
      id="imageUrl"
      label="Image Url"
      placeholder="Please enter a Image Url"
    />
    <TextInput
      rows={0}
      value={address}
      on:input={(event) => (address = event.target.value)}
      type="text"
      id="address"
      label="Address"
      placeholder="Please enter a address"
    />
    <TextInput
      rows={0}
      value={email}
      on:input={(event) => (email = event.target.value)}
      type="text"
      id="email"
      label="Email"
      placeholder="Please Enter a Email"
    />
    <TextInput
      rows={4}
      value={description}
      on:input={(event) => (description = event.target.value)}
      type="textarea"
      id="description"
      label="Description"
      placeholder="Description"
    />
    <Button content="Save" type="Submit" variant="containe" />
  </form>
</main>
<Meetup {meetups} />

<style>
  main {
    margin-top: 5rem;
  }
  form {
    width: 30rem;
    max-width: 90%;
    margin: 7rem auto;
  }
</style>
