<script lang="ts">
  import { Form, FormControl, FormField, FormItem, FormLabel, FormMessage } from '@shadcn/svelte';
  import { Input } from '$lib/components/ui/input';
  import { Textarea } from '$lib/components/ui/textarea';
  import { Button } from '$lib/components/ui/button';
  import { enhance } from '$app/forms';
  import { z } from 'zod';
  import { superValidate } from 'sveltekit-superforms/client';

  const contactSchema = z.object({
    name: z.string().min(2, { message: 'Name is required' }),
    email: z.string().email({ message: 'Invalid email address' }),
    message: z.string().min(10, { message: 'Message is required' })
  });

  const contactForm = superValidate(contactSchema, {
    validateOnMount: true
  });
  
  const handleSubmit = async (event: Event) => {
    const formData = await contactForm.handleSubmit(event);
    if (formData) {
      // Here, you'd typically send 'formData' to your backend for processing
      console.log('Form data submitted:', formData);
    }
  };

</script>

<div class="container mx-auto max-w-2xl p-8">

  <h1 class="text-3xl font-bold mb-6">Contact Us</h1>

  <Form {contactForm} on:submit={handleSubmit} use:enhance>

    <FormField name="name" let:error>
      <FormItem class="mb-4">
        <FormLabel>Your Name</FormLabel>
        <FormControl>
          <Input name="name" />
        </FormControl>
        <FormMessage>{error}</FormMessage>
      </FormItem>
    </FormField>

    <FormField name="email" let:error>
      <FormItem class="mb-4">
        <FormLabel>Your Email</FormLabel>
        <FormControl>
          <Input name="email" type="email" />
        </FormControl>
        <FormMessage>{error}</FormMessage>
      </FormItem>
    </FormField>

    <FormField name="message" let:error>
      <FormItem class="mb-4">
        <FormLabel>Your Message</FormLabel>
        <FormControl>
          <Textarea name="message" rows={5} />
        </FormControl>
        <FormMessage>{error}</FormMessage>
      </FormItem>
    </FormField>

    <Button type="submit" class="w-full">Submit</Button>

  </Form>

  <div class="mt-8">
    <p>You can also reach us at:</p>
    <p>Email: <a href="mailto:contact@chapi.dev">contact@chapi.dev</a></p>
    <p>Phone: +584125867955</p>
    <p>GitHub: <a href="https://github.com/chapig" target="_blank">github.com/chapig</a></p>
  </div>
</div>